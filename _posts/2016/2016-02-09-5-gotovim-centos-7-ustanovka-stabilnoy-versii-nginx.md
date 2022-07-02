---
title: "5 - Готовим CentOS 7. Установка стабильной версии nginx"
date: "2016-02-09"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/xXghX3y0ozk?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

 Создадим файл

```
nano -w /etc/yum.repos.d/nginx.repo
```

И с таким содержимым

\[nginx\] name=nginx repo baseurl=http://nginx.org/packages/centos/7/$basearch/ gpgcheck=0 enabled=1

Установим

```
yum install nginx -y
```

Проверяем

```
nginx -v
```

Запускаем

```
systemctl start nginx
systemctl status nginx
nmap localhost
```

Можно обратиться на сайт с виндос http://test.dev и увидим Welcome to nginx! Выставляем в автозагрузку nginx

```
systemctl enable nginx
```

Дополнительная иформация Стандартные порты и пути к файлам Nginx /etc/nginx/ - директория содержащая файлы настроек Nginx сервера; /etc/nginx/conf.d/ - директория содержащая файлы настроек SSL и виртуальных хостов (vhost); /etc/nginx/nginx.conf - основной файл настроек; /var/log/nginx/error.log - логи ошибок; /var/log/nginx/access.log - логи доступа; /usr/share/nginx/html/ - корневая директория сайта по умолчанию (document root); TCP 80 - HTTP порт по умолчанию для Nginx; TCP 443 - HTTPS порт по умолчанию для Nginx.
