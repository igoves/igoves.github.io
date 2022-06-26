---
title: "6 - Готовим CentOS 7. Установка PHP7"
date: "2016-02-10"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/GOgbR6MJESM?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

 Устанавливаем epel-release

```
yum install epel-release -y && cd /tmp	
```

Качаем репозиторий

```
wget http://rpms.remirepo.net/enterprise/remi-release-7.rpm
```

Добавляем репозиторий

```
rpm -Uvh remi-release-7*.rpm
```

Устанавливаем основные компоненты

```
yum --enablerepo=remi-php70 install php70-php php70-php-common php70-php-fpm php70-php-cli php70-php-opcache php70-php-pecl-apcu php70-php-process php70-php-xml php70-php-gd php70-php-mbstring -y
```

Проверяем

```
php70 -v
```

Стартуем php-fpm

```
systemctl start php70-php-fpm
```

Проверяем

```
systemctl status php70-php-fpm
```

Проверяем

```
php70 -a
echo 1+1;
> 2
exit
```

Отлично php 7 установлен! Выставляем в автозагрузку php

```
systemctl enable php70-php-fpm
```
