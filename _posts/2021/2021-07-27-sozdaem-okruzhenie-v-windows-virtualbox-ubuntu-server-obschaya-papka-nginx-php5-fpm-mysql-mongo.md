---
title: "Создаем окружение в Windows > VirtualBox > Ubuntu Server > общая папка (nginx + php5-fpm + mysql + mongo)"
categories: 
  - "note"
tags: 
  - "linux"
  - "server"
  - "virtualbox"
---

![Создаем окружение в Windows > VirtualBox > Ubuntu Server > общая папка (nginx + php5-fpm + mysql + mongo)](images/1435074483_hnck4560.png "Создаем окружение в Windows > VirtualBox > Ubuntu Server > общая папка (nginx + php5-fpm + mysql + mongo)")

  
Качаем и устанавливаем VirtualBox  
[https://www.virtualbox.org/wiki/Downloads](https://dev.xfor.top/go/aHR0cHM6Ly93d3cudmlydHVhbGJveC5vcmcvd2lraS9Eb3dubG9hZHM%3D)  
  
Качаем и устанавливаем Ubuntu Server 14.04 на VirtualBox  
[http://www.ubuntu.com/download/server](https://dev.xfor.top/go/aHR0cDovL3d3dy51YnVudHUuY29tL2Rvd25sb2FkL3NlcnZlcg%3D%3D)  
  
Обновляемся

```
sudo apt-get update
sudo apt-get upgrade
```

  
**Настраиваем общую папку**  
\- в настройках виртуальной машины добавляем общую папку  
\- в окне виртуалки -> устройства -> подключить образ диска Дополнительной гостевой ос  
\- монтируем привод и запускаем VboxLinuxAdditions.run

```
sudo mount /dev/cdrom /mnt
sudo apt-get install dkms build-essential linux-headers-$(uname -r)
cd /mnt && sudo sh ./VBoxLinuxAdditions.run
```

  
\- создаем папку в виртуалке где будет общая папка проекта

```
sudo mkdir -p /var/wwww/project.dev
```

  
\- монтируем общую папку

```
sudo mount -t vboxsf project.dev /var/wwww/project.dev
```

  
\- после этой команды директория /var/wwww/project.dev должна стать общей, смотрим что там у нас в каталоге теперь

```
ls -la /var/wwww/project.dev
```

  
\- если видим файлы нашего проекта, то все хорошо и можно добавить это монтирование в загрузку /etc/rc.local

```
sudo nano -w /etc/rc.local 
```

  
\- добавляем в самый низ строчку ( exit 0 - уберем )

```
mount -t vboxsf project.dev /var/wwww/project.dev
```

  
Теперь общая папка у нас есть.  
  
**Устанавливаем ssh сервер**, если таковой не поставили при установке.  
Причина 1) им удобней пользоваться чем в окне виртуалбокса  
Причина 2) подключаться к базам данных (через гуи) нужно используя ssh туннель, т.к. они все забиндены на localhost и считаю незачем это менять  
  
Устанавливаем Openssh

```
sudo apt-get install openssh-server
```

  
\- в virtualbox для нашей ubuntu у которой NAT адаптер, делаем проброс портов TCP порт хоста 22, порт гостя 22  
\- в сетевых подключениях виндовс смотрим внешний айпи нашей виртуалки **192.168.56.1**  
\- прописываем его в c:\\\\WINDOWS\\\\system32\\\\drivers\\\\etc\\\\hosts  

192.168.56.1 project.dev

  
Перезагружаемся

```
sudo reboot
```

  
Далее будем пользоваться виртуалкой через **Putty** ssh.  
Конектимся на project.dev порт 22. Авторизируемся.  
  
**Устанавливаем Nginx**  
\- прописываем в конец файла /etc/apt/sources.list следующее:  

deb http://nginx.org/packages/ubuntu/ trusty nginx  
deb-src http://nginx.org/packages/ubuntu/ trusty nginx

  
\- добавляем ключ

```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys ABF5BD827BD9BF62
```

  
\- обновляем репозитории и устанавливаем

```
sudo apt-get update && sudo apt-get install nginx
```

  
\- аналогично, как с ssh пробрасываем 80 порт. TCP порт хоста 80, порт гостя 80  
\- теперь при попытке зайти на http://project.dev мы увидим _Welcome to nginx!_  
  
**Устанавливаем php5-fpm**

```
sudo apt-get install php5-fpm php5-gd php5-mysql php5-mongo
```

  
Теперь нужно настроить Nginx что бы работал с PHP.  
\- сначала в /etc/nginx/conf.d/default.conf смотрим где хранится html c Welcome to nginx!

```
nano /etc/nginx/conf.d/default.conf
```

  
\- видим root /usr/share/nginx/html, по этому пути создадим index.php с <?php phpinfo();

```
sudo nano -w /usr/share/nginx/html/index.php
```

  
\- теперь если обратиться на http://project.dev/index.php он не откроется, но скачается =)  
\- правим /etc/nginx/nginx.conf  

user www-data;

  
\- правим /etc/nginx/conf.d/default.conf

```
sudo nano -w /etc/nginx/conf.d/default.conf
```

  
\- ключевые моменты (минимум для старта php):

```
location ~ \\.php$ {
	fastcgi_pass   unix:/var/run/php5-fpm.sock;
	fastcgi_param  SCRIPT_FILENAME  /usr/share/nginx/html$fastcgi_script_n$
	include        fastcgi_params;
}
```

  
\- перезапускаем nginx и php5-fpm

```
sudo service nginx restart && sudo service php5-fpm restart
```

  
\- проверяем  
по http://project.dev/ _Welcome to nginx!_  
по http://project.dev/index.php открывается _phpinfo_  
  
**Ставим заглушку sendmail**  
\- создаем shell-скрипт /usr/bin/fakesendmail.sh со следующим содержимым:

```
#!/bin/sh 
prefix="/var/mail/sendmail/new"
numPath="/var/mail/sendmail"
if [ ! -f $numPath/num ]; then 
echo "0" > $numPath/num 
fi 
num=`cat $numPath/num` 
num=$(($num + 1)) 
echo $num > $numPath/num 
name="$prefix/letter_$num.txt"
while read line 
do 
echo $line >> $name
done 
chmod 777 $name
/bin/true
```

  
\- делаем файл исполняемым и назначим его владельцем пользователя root

```
sudo chown root:root /usr/bin/fakesendmail.sh
sudo chmod 755 /usr/bin/fakesendmail.sh
```

  
\- нужно создать особую структуру каталогов и дать права на запись в них

```
sudo mkdir /var/mail/sendmail
cd /var/mail/sendmail
sudo mkdir cur
sudo mkdir new
sudo mkdir tmp
sudo chmod -R 777 /var/mail/sendmail	
```

  
\- настраиваем php на работу с заллушкой в /etc/php5/fpm/php.ini ставим параметр  

sendmail\_path = /usr/bin/fakesendmail.sh

  
\- перезапускаем php

```
sudo service php5-fpm restart
```

  
\- открываем наш тестовый /usr/share/nginx/html/index.php и дописываем функцию отправки письма  

```
mail("joecool@example.com", "My Subject", "Line 1\\nLine 2\\nLine 3");
```

  
\- обновляем страницу http://project.dev/index.php и проверяем каталог с письмом  
/var/mail/sendmail/new создался letter\_1.txt с отправленым нами письмом  
Заглушка готова.  
  
**Устанавливаем MySQL 5.6**

```
sudo apt-get install mysql-server-5.6
```

  
\- если используете гуи типа HeidiSQL то подключайтесь к 127.0.0.1 через ssh тунель  
Mysql готов.  
  
**Устанавливаем Mongo**  
\- добавляем ключ

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
```

  
\- добавляем репозиторий

```
echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list
```

  
\- обновляем

```
sudo apt-get update
```

  
\- устанавливаем

```
sudo apt-get install -y mongodb-org
```

  
\- если используете гуи типа MongoVUE то подключайтесь к 127.0.0.1 через ssh тунель  
Mongo готов.  
  
Чистим систему от старых и ненужных пакетов

```
sudo apt-get autoclean
sudo apt-get autoremove	
```

  
Теперь изменяем /etc/nginx/conf.d/default.conf на нашу общую папку /var/www/project.dev

```
location / {
	...
	root   /var/www/project.dev;
	index  index.php index.html index.htm;
	...
}
location ~ \\.php$ {
	...
	fastcgi_param  SCRIPT_FILENAME  /var/www/project.dev$fastcgi_script_name;
	...
}
```

  
\- перезапускаем nginx и php5-fpm

```
sudo service nginx restart && sudo service php5-fpm restart
```

  
Все готово.  
  
**Дополнительно**  
  
Старт VM машины из cmd

```
c:/"Program Files"/Oracle/VirtualBox/VBoxManage startvm "vm_name" --type headless
```

  
Стоп VM машины из cmd

```
c:/"Program Files"/Oracle/VirtualBox/VBoxManage controlvm "vm_name" acpipowerbutton
```

  
Файлы конфигурации  
nginx  

/etc/nginx/nginx.conf  
/etc/nginx/conf.d/default.conf

  
php  

/etc/php5/fpm/php.ini  
/etc/php5/fpm/pool.d/www.conf

  
mysql  

/etc/mysql/my.cnf

  
mongo  

/usr/local/etc/mongodb.conf  
/etc/mongod.conf

  
Дальнейшая конфигурация и настройка каждой части окружения, очень индивидуальна.  
  
**Полезные программки**

```
sudo apt-get install htop
sudo apt-get install iotop
sudo apt-get install cbm
sudo apt-get install mc
```

  
**Послесловие**  
Альтернативный вариант создания окружения. Но это способ для тех кому не нужно ковыряться в настройках например nginx\\'a.  
Скачать **Vagrant**. Установить. Потом зайти **https://puphpet.com/** и создать конфигурацию сервера.  
После распаковать себе в проект архив конфигурации.  
Выполнить в консоли **vagrant up**.  
Виртуальная машина скачается, установится, сконфигурируется и поставит все программы которые указаны в конфигурации.  
Но, суть вагранта такова что конфигурируется сервер непосредственно в файле конфигурации, а не после того как машина развернута. А из за этого возникают проблемы тонкой настройки виртуального сервера.
