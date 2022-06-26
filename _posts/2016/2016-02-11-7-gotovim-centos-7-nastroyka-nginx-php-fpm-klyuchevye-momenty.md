---
title: "7 - Готовим CentOS 7. Настройка nginx + php-fpm ключевые моменты"
date: "2016-02-11"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/fIr7V-XwaB8?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

 Проверяем что nginx и php работают

```
systemctl status nginx
systemctl status php70-php-fpm
```

Основной файл конфигурации nginx

/etc/nginx/nginx.conf

Создаем файл конфигурации для нашего проекта test.dev

```
nano -w /etc/nginx/conf.d/test.dev.conf
server {
    listen       80;
    server_name  test.dev;
	root   /var/www/test.dev;
    location / {
        index  index.html index.php;
    }
}
```

Перезапускаем

```
systemctl restart nginx
```

3 раза ( после каждого прохода этих команд пробуем зайти на http://test.dev/ ) пока selinux нас не пустит

```
grep nginx /var/log/audit/audit.log | audit2allow -m nginx > nginx.te 
grep nginx /var/log/audit/audit.log | audit2allow -M nginx 
semodule -i nginx.pp
```

Пробуем открыть http://test.dev/index.html

если работает html по новому адресу то дописываем секцию обработки php

```
nano -w /etc/nginx/conf.d/test.dev.conf
```

```
location ~ \\.php$ {
	try_files $uri =404;
	fastcgi_pass 127.0.0.1:9000;
	fastcgi_param SCRIPT_FILENAME $request_filename;
	fastcgi_index index.php;
	fastcgi_read_timeout 30;
	fastcgi_buffers 16 16k;
	fastcgi_buffer_size 32k;
	include	fastcgi_params;
}
```

Перезапускаем

```
systemctl restart nginx
```

Посмотреть selunux что связано с http и при надобности включить что необходимо

```
sestatus -b | grep -i httpd
```

Найдем где храняться наши настройки для php7

```
php70 -i | grep "Loaded Configuration File"
```

/etc/opt/remi/php70/php.ini
