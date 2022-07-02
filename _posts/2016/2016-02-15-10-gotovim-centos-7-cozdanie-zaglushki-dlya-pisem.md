---
title: "10 - Готовим CentOS 7. Cоздание заглушки для писем"
date: "2016-02-15"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/N36zpoxX_zA?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

\- создаем shell-скрипт:

```
nano -w /usr/bin/fakesendmail.sh
```

со следующим содержимым:

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

\- делаем файл исполняемым

```
chmod +x /usr/bin/fakesendmail.sh
chmod 755 /usr/bin/fakesendmail.sh
```

```
mkdir /var/mail/sendmail
cd /var/mail/sendmail
mkdir cur && mkdir new && mkdir tmp
chmod -R 777 /var/mail/sendmail	
```

Найдем где храняться наши настройки для php7

```
php70 -i | grep "Loaded Configuration File"
```

\- настраиваем php на работу с заглушкой в /etc/opt/remi/php70/php.ini ставим параметр

```
nano -w /etc/opt/remi/php70/php.ini
sendmail_path = /usr/bin/fakesendmail.sh
```

\- перезапускаем php

```
systemctl restart php70-php-fpm
```

```
sestatus -b | grep -i sendmail
setsebool -P httpd_can_sendmail 1
```

\- cоздадим файл /var/www/test.dev/3.php и дописываем функцию отправки письма

```
nano -w /var/www/test.dev/3.php
```

```
<?php mail("test@test.dev", "My Subject", "Line 1\\nLine 2\\nLine 3"); echo 'sended';
```

\- обновляем страницу http://test.dev/3.php и проверяем каталог с письмом /var/mail/sendmail/new создался letter\_1.txt с отправленым нами письмом

```
ls /var/mail/sendmail/new
grep mail /var/log/audit/audit.log
```

Запускаем эти команды для selinux (в моем случае это 5 раз пока не начали отправляться заполненые письма)

```
grep mail /var/log/audit/audit.log | audit2allow -m mail > mail.te 
grep mail /var/log/audit/audit.log | audit2allow -M mail 
semodule -i mail.pp
```

Заглушка готова.
