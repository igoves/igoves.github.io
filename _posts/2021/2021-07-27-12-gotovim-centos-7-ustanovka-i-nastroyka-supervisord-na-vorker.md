---
title: "12 - Готовим CentOS 7. Установка и настройка supervisord на воркер"
date: ""
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/3mnYknV_ifM?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

  
  
Утсановка  

```
yum install python-setuptools -y
easy_install pip
pip install supervisor
supervisord --version
mkdir -p /etc/supervisord
echo_supervisord_conf > /etc/supervisord/supervisord.conf
```

  
Создаем файл автозагрузки  

```
nano -w /usr/lib/systemd/system/supervisord.service
```

  
С таким содержимым  

```
[Unit]
Description=supervisord - Supervisor process control system for UNIX
Documentation=http://supervisord.org
After=network.target

[Service]
Type=forking
ExecStart=/usr/bin/supervisord -c /etc/supervisord/supervisord.conf
ExecReload=/usr/bin/supervisorctl reload
ExecStop=/usr/bin/supervisorctl shutdown
User=nginx

[Install]
WantedBy=multi-user.target
```

  
Стартуем, смотрим статус, добавляем в автозагрузку  

```
systemctl start supervisord
systemctl status supervisord
systemctl enable supervisord
```

  
Сконфигурируем  

```
nano -w /etc/supervisord/supervisord.conf
```

  
в самом низу добавляем настройки для нужного воркера:  

```
[program:worker]
command=/opt/remi/php70/root/bin/php /var/www/test.dev/worker.php
numprocs=1
directory=/var/www/test.dev
autostart=true
autorestart=true
stopsignal=KILL
```

  
Для запуска нескольких копий одного процесса необходимо также указать параметр process\_name для определения уникального имени процесса  

```
[program:worker]
command=/opt/remi/php70/root/bin/php /var/www/test.dev/worker.php
process_name=%(program_name)s_%(process_num)02d
numprocs=10
directory=/var/www/test.dev
autostart=true
autorestart=true
stopsignal=KILL
```

  
Запустит 10 одновременных процессов указанного скрипта  
  
Исправляем пути на абсолютные в нашем producer.php и worker.php  

```
require_once '/var/www/test.dev/vendor/autoload.php';
$file = '/var/www/test.dev/data.txt';
```

  
Перезапускаем  

```
systemctl restart supervisord
```

  
**Дополнительно**  
для supervisord есть плагин **Superlance**  
Включает в себя набор утилит  
**httpok** - отправляет гет запрос по урлу, если запрос не приходит или отваливается по таймауту то перезапускает процесс  
**crashmail** - отправляет на поучту письмо в случае неполадки  
**memmon** \- мониторит использование памяти, и перезапускает процесс если привышает лимит указаный в конфиге  
**crashmailbatch** \- аналогичный crashmail, разница только в том что уведамления группируются за определенный период и отправляется пучком.  
**fatalmailbatch** \- отправляет уведомление когда супервизор много раз фейлится при запуске, так же уведомления группируются перед отправкой письма  
**crashsms** \- аналогично crashmailbatch, отправляет смс через email шлюз.  
Документация [https://superlance.readthedocs.org/en/latest/](https://dev.xfor.top/go/aHR0cHM6Ly9zdXBlcmxhbmNlLnJlYWR0aGVkb2NzLm9yZy9lbi9sYXRlc3Qv)  
Установить  

```
easy_install superlance
```
