---
title: "Примеры типовых docker-compose файлов"
date: "2020-08-13"
categories: 
  - "note"
tags: 
  - "compose"
  - "docker"
---

Запускаем контейнер php +apache

```
version: '3'

services:
    php:
        image: nanoninja/php-fpm:latest
        restart: always
        volumes:
            - ./web:/var/www/html
    apache2:
        image: webdevops/apache:latest
        environment:
            - WEB_PHP_SOCKET=php:9000
            - WEB_DOCUMENT_ROOT=/var/www/html
        volumes:
            - ./web:/var/www/html
        ports:
            - 80:80
        links:
            - php
```

nginx + php-fpm + composer + mongodb + redis + mailhog

```
version: "3.7"
services:

    web:
        image: nginx:latest
        container_name: nginx
        ports:
            - "80:80"
            - "443:443"
        restart: always
        volumes:
            - "./etc/nginx:/etc/nginx/conf.d"
            - "./etc/ssl:/etc/ssl"
            - "./site.loc:/var/www/site.loc"
        depends_on:
            - "php"
            - "mongodb"
            - "redis"
        links:
            - php
            
    php:
        image: nanoninja/php-fpm
        restart: always
        volumes:
            - "./etc/php/php.ini:/usr/local/etc/php/conf.d/php.ini"
            - "./site.loc:/var/www/site.loc"

    composer:
        image: composer/composer
        volumes:
            - "./site.loc:/var/www/site.loc"
        command: install
            
    mongodb:
        image: mongo
        container_name: mongo
        restart: always
        volumes:
            - "/SITE/DEV/data/db/mongo:/data/db"
        ports:
            - "27017:27017"
        # command: --storageEngine wiredTiger
            
    redis:
        image: redis
        container_name: redis
        restart: always
        command: redis-server --appendonly yes
        ports:
            - "6379:6379"
        volumes:
          - "./data:/data"
          
    mailhog:
        image: mailhog/mailhog:v1.0.0
        ports:
            - "1025:1025"
            - "8025:8025"
      
```

nginx + mysql

```
version: '3.3'
services:
  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: 'db'
      MYSQL_USER: 'user'
      MYSQL_PASSWORD: 'password'
      MYSQL_ROOT_PASSWORD: 'password'
    ports:
      - '3306:3306'
    expose:
      - '3306'
    volumes:
      - my-db:/var/lib/mysql
volumes:
  my-db:
```
