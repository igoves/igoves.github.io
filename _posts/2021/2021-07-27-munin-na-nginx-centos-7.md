---
title: "Munin на nginx CentOS 7"
categories: 
  - "note"
---

```
yum install munin munin-node -y
```

  
Раскомментируем строки и укажем нужные пути в munin.conf  

```
nano /etc/munin/munin.conf
```

dbdir /var/lib/munin  
htmldir /var/www/html/munin  
logdir /var/log/munin  
rundir /var/run/munin  
tmpldir /etc/munin/templates  
\# a simple host tree  
\[vashdomen.ru\]  
address 127.0.0.1  
use\_node\_name yes

  

```
nano /etc/nginx/conf.d/default.conf
```

location /nginx\_status {  
stub\_status on;  
access\_log off;  
allow 127.0.0.1;  
deny all;  
}

  

```
nano /etc/nginx/conf.d/vashdomen.ru.conf
```

location ^~ /munin {  
alias /var/www/html/munin;  
auth\_basic \\"Admin Zone\\";  
auth\_basic\_user\_file /etc/munin/munin-htpasswd;  
}

  
Ганерируем пароль для просмотра статистики  

```
htpasswd -c /etc/munin/munin-htpasswd admin
```

  
посмотреть плагины которые есть  

```
ls /usr/share/munin/plugins
```

  
посмотреть плагины которые включены  

```
ls /etc/munin/plugins
```

  
Включаем плагины munin для nginx:  

```
ln -s /usr/share/munin/plugins/nginx_status /etc/munin/plugins/nginx_status
ln -s /usr/share/munin/plugins/nginx_request /etc/munin/plugins/nginx_request
```

  
Дополняем файл munin-node следующим текстом:  

```
nano /etc/munin/plugin-conf.d/munin-node
```

\[nginx\*\]  
env.url http://localhost/nginx\_status

  
настройки самой ноды  

```
nano /etc/munin/munin-node.conf	
```

  
Проверяем конфигурационный файл и перечитываем правила  

```
nginx -t
nginx -s reload
```

  
Запускаем munin-node  

```
systemctl enable munin-node
systemctl start munin-node
```

  
Проверка работы плагинов  

```
munin-node-configure --suggest
```

  
Посмотреть идет ли сбор данных с nginx  

```
munin-node-configure --suggest | grep nginx
```

  
Заходим по адрессу и смотрим статистику  
http://vashdomen.ru/munin/  
  
Перезагрузка munin-node:  

```
systemctl restart munin-node
```

  
Команда покажет какие плагины можно добавить в систему мониторинга  

```
munin-node-configure --shell
```

  
автоматически создаст симлинки на ВСЕ рабочие плагины  

```
munin-node-configure --shell | sh -x
```

  
Шаблон для munin на твиттер бутстрап 3  
https://github.com/jonnymccullagh/munstrap
