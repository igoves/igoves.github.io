---
title: "8 - Готовим CentOS 7. Установка и настройка стабильной версии MongoDB"
date: "2016-02-12"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/pIXbbR3qERk?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

 Создадим файл

```
nano -w /etc/yum.repos.d/mongodb-org-3.2.repo
```

Запишем в него

```
[mongodb-org-3.2]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.2/x86_64/
gpgcheck=0
enabled=1
```

Установим

```
yum -y install mongodb-org
semanage port -a -t mongod_port_t -p tcp 27017
```

Запустим

```
systemctl start mongod
```

Проверим

```
mongo
> db.version()
> exit
```

Предупреждение 1 **WARNING: Readahead for /var/lib/mongo is set to 4096KB** Предупреждение 2 **WARNING: /sys/kernel/mm/transparent\_hugepage/enabled is \\'always\\'** Предупреждение 3 **WARNING: /sys/kernel/mm/transparent\_hugepage/defrag is \\'always\\'.** Предупреждение 4 **WARNING: soft rlimits too low. rlimits set to 4096 processes, 64000 files.**

Сейчас это будем исправлять

```
nano -w /etc/init.d/mongod
```

Перед Starting mongod вставляем

```
if test -f /sys/kernel/mm/transparent_hugepage/enabled; then
   echo never > /sys/kernel/mm/transparent_hugepage/enabled
fi
if test -f /sys/kernel/mm/transparent_hugepage/defrag; then
   echo never > /sys/kernel/mm/transparent_hugepage/defrag
fi
```

Перезапускаем

```
systemctl restart mongod
systemctl daemon-reload
```

```
df -h
blockdev --report
blockdev --setra 256 /dev/mapper/centos-root
```

Добавляем в автозагрузку

```
nano -w /etc/rc.local
```

```
blockdev --setra 256 /dev/mapper/centos-root
```

Перезагружаем

```
systemctl restart mongod
```

Почитать про предпочтительные лимиты для монго можно здесь https://docs.mongodb.org/manual/reference/ulimit/

```
ls /etc/security/limits.d/
```

```
nano -w /etc/security/limits.d/20-nproc.conf 
```

проставляем как просит монго 64000

Перезапустим

```
systemctl restart mongod
```

Проверим

```
systemctl status mongod
```

Добавим в автозагрузку

```
systemctl enable mongod
mongo
exit
```

настройки /etc/mongod.conf

доставим поддержку mongo в нашем php

```
yum install php70-php-pecl-mongodb -y
```

перезепустим php

```
systemctl restart php70-php-fpm
```

Проверяем что расширение установлено и доступно

```
php70 -m | grep -i mongodb
```

В ответ получить должны **mongodb**

Создаем файл

```
nano -w /var/www/test.dev/mongo.php
```

и пишем в него

```
<?php $m = new MongoDB\\Driver\\Manager("mongodb://localhost:27017");
```

Выполняем, если ошибки нет, то все хорошо.
