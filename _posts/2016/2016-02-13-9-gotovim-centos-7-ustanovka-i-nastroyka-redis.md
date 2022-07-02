---
title: "9 - Готовим CentOS 7. Установка и настройка Redis"
date: "2016-02-13"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/eD5orO2kuBw?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

```
yum install redis -y
```

(для успешного выполнения этой команды, нужен epel-release мы его установили вместе с php ранее)

Старт

```
systemctl start redis
```

Смотрим статус

```
systemctl status redis
```

Подключаемся к redis

```
redis-cli -h 127.0.0.1 -p 6379 
```

```
ping
INFO
exit
```

Ставим в автозагрузку

```
systemctl enable redis.service
```

Настройки

/etc/redis.conf /etc/redis-sentinel.conf

```
nano -w /etc/redis.conf
```

tcp-keepalive 60 bind 127.0.0.1 appendonly yes appendfilename \\"appendonly.aof\\"

В случае с AOF, Redis ведёт лог операций, которые выполняют клиенты и записывает их в файл (по умолчанию каждую секунду). AOF это аббревиатура от Append Only File, а это означает то, что Redis не изменяет уже записанные данные, а лишь добавляет новые в конец. Благодаря тому, что при использовании AOF, Redis по умолчанию пишет данные на диск каждую секунду, максимум, что вы теряете в случае сбоя при использовании этого режима — это 1 секунда.

Перезагружаем

```
systemctl restart redis
```

Если заглянуть в /var/log/redis/redis.log То можно увидеть два предупреждения **WARNING overcommit\_memory is set to 0** **WARNING: The TCP backlog setting of 511 cannot be enforced because /proc/sys/net/core/somaxconn is set to the lower value of 128** Исправим первое

```
nano /etc/sysctl.conf
```

вставляем строчку

vm.overcommit\_memory = 1

выполняем команду

```
sysctl vm.overcommit_memory=1
```

Исправим второе

```
nano /etc/rc.local
```

Добавляем строчку

sysctl -w net.core.somaxconn=65535

и заодно выполним ее в консоли

```
sysctl -w net.core.somaxconn=65535
```

Перезагружаем и смотрим в /var/log/redis/redis.log что все теперь впорядке

```
systemctl restart redis
```

Осталось установить модуль redis для php Так как для php70 его в портах нет, придеться компилировать самому

```
cd /tmp
wget https://github.com/phpredis/phpredis/archive/php7.zip
yum install unzip -y
unzip php7.zip
cd phpredis-php7
yum install php70-php-devel m4 autoconf -y
/opt/remi/php70/root/usr/bin/phpize
./configure CFLAGS="-O3" --with-php-config=/opt/remi/php70/root/usr/bin/php-config
make clean all
make test
cp /tmp/phpredis-php7/modules/redis.so /opt/remi/php70/root/lib64/php/modules/
echo extension=redis.so > /etc/opt/remi/php70/php.d/redis.ini
rm -rf /tmp/php7.zip && rm -rf /tmp/phpredis-php7
```

Рестарт

```
systemctl restart php70-php-fpm
```

Проверим

```
php70 -m | grep -i redis
```

В ответ **redis** Значит модуль стал. Создаем тестовый файл

```
nano -w /var/www/test.dev/2.php
```

```
<?php
$redis = new Redis();
$redis->connect('localhost:6379');
```

Проверяем,если ошибка, что класс Redis не существует, не вылетела, то все отлично. Можно так же запустить бенчмарк, посмотреть как быстро работатет ваш redis

```
nano -w /var/www/test.dev/2.php
```

```
try {
    $redis = new Redis();
    $redis->connect('localhost:6379');
} catch(RedisException $e) {
    exit('Connect error');
}
$benchmark = microtime(true);
for($i=0;$i < 80000; $i++)
    $redis->set('key','value');

echo microtime(true) - $benchmark;
```

Ошибка **Uncaught RedisException: Redis server went away** Опять этот SELinux......

```
setsebool -P httpd_can_network_connect=1
semodule -r redis
```

Не плохо так же перенести стандартные php сессии на redis, для этого В php.ini прописываем ( наши сессии теперь будут храниться в redis)

```
nano -w /etc/opt/remi/php70/php-fpm.d/www.conf
```

```
php_value[session.save_handler] = redis
php_value[session.save_path]    = tcp://127.0.0.1:6379
# если с паролем то
# session.save_path = "tcp://127.0.0.1:6379?auth=yourverycomplexpasswordhere"
```

или прямо в файле php

```
ini_set('session.save_handler', 'redis');
ini_set('session.save_path',    'tcp://127.0.0.1:6379');
```

Настройки /etc/redis/redis.conf Перезапускаем

```
systemctl restart redis
systemctl restart php70-php-fpm
```

Дописываем в наш файлик

```
nano -w /var/www/test.dev/2.php
```

```
session_start();
```

Запускаем в браузере. И проверяем создалась ли сессия у нас в redis.

И не забываем посматривать в /var/log/redis
