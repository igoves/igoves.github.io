---
title: "Ответы на вопросы компания MindK на темы Environment Automation and Services"
date: "2020-08-21"
categories: 
  - "note"
tags: 
  - "answers"
  - "interview"
---

**Environment Automation**

- Знаком с базовыми принципами Continuous Integration.  
    Это практика разработки ПО, которая заключается в слиянии рабочих копий в общую основную ветвь разработки и выполнении частых автоматизированных сборок проекта выполнении тестов и доставки его на продакт.  
    
- Знаком с одной из систем Continuous Integration.  
    Jenkins, TeamCity, Travis CI  
    
- Настраивал простую сборку веб-проекта из системы контроля версий (например, GIT) на Linux сервер.  
    Hook Pre-commit, post-commit  
    
- Имею практический опыт работы с Docker.  
    Программное обеспечение для автоматизации развёртывания и управления приложениями в средах с поддержкой контейнеризации  
    
- Знаю как попасть по ssh в Docker контейнер.  
    Для этого нужно установить и запустить на докер контейнере sshd  
    `apt-get install openssh-server  
    mkdir /var/run/sshd  
    chmod 0755 /var/run/sshd  
    /usr/sbin/sshd  
    useradd --create-home --shell /bin/bash --groups sudo username ## includes 'sudo'  
    passwd username ## Enter a password`  
    А для выполнения произвольных команд достаточно попасть на баш  
    `docker ps  
    docker exec -it bash`
- Знаю что такое и есть опыт работы с docker-compose.  
    Файл compose используется для определения необходимых для приложения сервисов. Пример, подымаем веб = пхп + нджинкс:

```
version: '3'
services:
  web:
    image: nginx:alpine
    volumes:
      - "./etc/default.conf:/etc/nginx/conf.d/default.conf"
      - ".:/var/www/html"
      - "./etc/default.template.conf:/etc/nginx/conf.d/default.template"
    ports:
      - "80:80"
    environment:
      - NGINX_HOST=${NGINX_HOST}
    command: /bin/sh -c "envsubst '$$NGINX_HOST' < /etc/nginx/conf.d/default.template > /etc/nginx/conf.d/default.conf && nginx -g 'daemon off;'"
    restart: always
    depends_on:
      - php
  php:
    image: nanoninja/php-fpm:${PHP_VERSION}
    restart: always
    volumes:
      - "./etc/php.ini:/usr/local/etc/php/conf.d/php.ini"
      - .:/var/www/html
```

**Services**

- Знаю сервисы Firebase и есть опыт работы с ними  
    Firebase дает инструменты для быстрой разработки приложений  
    
- Realtime Database  
    Облачная NoSQL база данных  
    
- Cloud Functions  
    Выполнение бекенд кода на гугловском облаке  
    
- Authentication  
    Бекенд сервисы (телефон, пароль, провайдеры типа твиттер и фейсбук) SDK для авторизации  
    
- Cloud Storage  
    Облачное хранилище для файлов  
    
- Знаю сервисы AWS и есть опыт работы с ними.  
    https://aws.amazon.com/ru/  
    
- Есть опыт работы с Google API (e.g. Google Maps API, OAUTH).  
    https://developers.google.com/apis-explorer/#p/
