---
title: "Пара настроек файла .htaccess которые вам могут пригодиться"
date: ""
categories: 
  - "note"
---

Устанавливаем индексный файл для сайта

```
DirectoryIndex имя_файла
```

  
Кодировка по умолчанию

```
CharsetDefault ваша_кодировка
```

  
Запрет доступа с определенного ip

```
order allow denydeny from alldeny from <ваш ip>
```

  
Установка пароля на директорию

```
AuthName "Private zone"AuthType BasicAuthUserFile /pub/home/твой_логин/.htpasswdrequire valid-user</Files>
```

  
Изменение максимального размера для загружаемых файлов

```
php_value upload_max_filesize 40Mphp_value post_max_size 40M
```

  
Защита сайта от вставки изображений с других ресурсов

```
RewriteEngine onRewriteCond %{HTTP_REFERER} !^$RewriteCond %{HTTP_REFERER} !^http(s)?://(www\\.)?yourdomain.com [NC]RewriteRule \\.(jpg|jpeg|png|gif)$ - [NC,F,L]
```

  
Блокировка посетителей, перешедших с определенного домена

```
<IfModule mod_rewrite.c>RewriteEngine onRewriteCond %{HTTP_REFERER} bannedurl1.com [NC,OR]RewriteCond %{HTTP_REFERER} bannedurl2.com [NC,OR]RewriteRule .* - [F]</ifModule>
```

  
Перенаправление на защищенное соединение HTTPS

```
RewriteEngine OnRewriteCond %{HTTPS} !onRewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI}
```
