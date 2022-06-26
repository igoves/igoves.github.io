---
title: "Установка программ на CentOS 6.6 ( nginx 1.8.0 + php-fpm 5.6 + mysql 5.6 + mongo 3.0 + sendmail )"
date: ""
categories: 
  - "php"
---

Ранее писал как [стартануть virtaulbox для разработки на локалке c ubuntu](https://dev.xfor.top/1846-sozdaem-okruzhenie-v-windows-virtualbox-ubuntu-server-obschaya-papka-nginx-php5-fpm-mysql-mongo.html) и таким же набором программ. А теперь, предположим мы арендовали VPS. Нам вручили ssh: ip, логин и пароль от голой машины CentOS.  
  

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/Ol0e9iGmHiA?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

  
  
Приступим!  
  
Тип ОС:

```
cat /proc/version
```

  
Версию ОС:

```
cat /etc/issue
```

  
Обновляемся

```
yum update -y
```

  
Ставим wget и nano если их нет

```
yum install wget nano -y
```

  
**Установка nginx 1.8.0**

```
wget http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm
rpm -i nginx-release-centos-6-0.el6.ngx.noarch.rpm
yum install nginx -y
chkconfig nginx on && service nginx start
```

  
**Установка php-fpm 5.6 и его компонтентов**

```
rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm
cd /etc/yum.repos.d
curl -O http://rpms.famillecollet.com/enterprise/remi.repo
yum install php php-fpm php-opcache php-gd php-mysql php-mongo -y --enablerepo=remi-php56
chkconfig php-fpm on && service php-fpm start
```

  
**Установка mysql 5.6**

```
cd ~
wget http://dev.mysql.com/get/mysql-community-release-el6-5.noarch.rpm
rpm -i mysql-community-release-el6-5.noarch.rpm
yum install mysql-community-server -y
chkconfig mysqld on && service mysqld start 
/usr/bin/mysql_secure_installation
```

  
**Установка mongo 3.0**

```
nano -w /etc/yum.repos.d/mongodb-org-3.0.repo
```

\[mongodb-org-3.0\]  
name=MongoDB Repository  
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.0/x86\_64/  
gpgcheck=0  
enabled=1

  

```
yum install mongodb-org -y
chkconfig mongod on && service mongod start
```

  
**Установка sendmail**

```
yum install sendmail -y
chkconfig sendmail on && service sendmail start
```

  
Проверяем что все запущено

```
netstat -tulpn
service sendmail status
```

  
На этом установка закончена.  
Дальше надо настроить каждый компонент.  
  
nginx

/etc/nginx/nginx.conf  
/etc/nginx/conf.d/default.conf

  
php

/etc/php5/fpm/php.ini  
/etc/php5/fpm/pool.d/www.conf

  
mysql

/etc/mysql/my.cnf

  
mongodb

/usr/local/etc/mongodb.conf  
/etc/mongod.conf

  
sendmail

/etc/mail/  
/etc/mail/sendmail.mc

Что бы письма отправленные с вашего сервера не попадали в спам нужно настроить SPF, DKIM и DMARC
