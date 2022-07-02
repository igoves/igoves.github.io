---
title: "14 - Готовим CentOS 7. Установка и настройка дополнительного софта"
date: "2016-02-19"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/Ssk2lGaKz1U?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

**Rkhunter** — это сканер различных видов локальных (потенциальных) уязвимостей (бэкдоров, эксплоитов и руткитов) со своей регулярно обновляемой базой.

```
yum install rkhunter -y
rkhunter --versioncheck
rkhunter --update
```

Вторым шагом будет создание снимка состояния установленной системы для rkhunter командой:

```
rkhunter --propupd
rkhunter --check
```

Настройка rkhunter Файл конфигурации /etc/rkhunter.conf После редактирования конфигурационного файла сохраните его и проверьте на наличие проблем, запустив

```
rkhunter -C
```

Запустим rkhunter для проверки системы, но добавим ключ -rwo, чтобы выводились только предупреждения:

```
rkhunter -c --enable all --disable none --rwo
```

**ClamAV** - это антивирус

```
yum -y install clamav-server clamav-data clamav-update clamav-filesystem clamav clamav-scanner-systemd clamav-devel clamav-lib clamav-server-systemd
```

```
nano -w  /etc/freshclam.conf
```

Закомментируем строчку Example

```
# Example
```

И добавим зеркал

```
DatabaseMirror db.us.clamav.net
DatabaseMirror db.de.clamav.net
DatabaseMirror db.jp.clamav.net
```

Обновим

```
freshclam
```

```
clamscan -ri /var/www/test.dev/
```

**Malware Detect** - программа для поиска и отлова malware

```
cd /tmp
wget http://www.rfxn.com/downloads/maldetect-current.tar.gz
tar xfz maldetect-current.tar.gz
cd maldetect-*
./install.sh
```

Настройки nano /usr/local/maldetect/conf.maldet Что бы просканировать директорию

```
maldet -a /var/www
```

Обновить программу

```
maldet -u
```

**inxi** - программа показывает железо на котором крутится

```
yum install inxi -y
inxi -F
```

Посмотреть список подключенных репозиториев в вашей системе

```
yum repolist	
```

Получить список процессов упорядоченных по используемой памяти, в мегабайтах (MB) :

```
ps axo rss,comm,pid \\
| awk '{ proc_list[$2]++; proc_list[$2 "," 1] += $1; } \\
END { for (proc in proc_list) { printf("%d\\t%s\\n", \\
proc_list[proc "," 1],proc); }}' | sort -n | tail -n 10 | sort -rn \\
| awk '{$1/=1024;printf "%.0fMB\\t",$1}{print $2}'
```

Просмотреть конфигурационный Файл без комментариев

```
grep ^[^#] somefile.conf
```

ну или например если это php.ini и там комментарий не через # а через ; то так

```
grep ^[^\\;] /etc/opt/remi/php70/php.ini
```

**SELinux** Проверить статус **getenforce** Enforcing (включен), Permissive (включен в режиме уведомлений), или Disabled (отключен) Временно отключить

```
setenforce 0
```

Временно включить

```
setenforce 1
```

Отключение selinux

```
nano -w /etc/selinux/config
```

Измените строку SELINUX= в файле /etc/selinux/config на

```
SELINUX=disabled
```

ТЕСТ Скорости ЗАПИСИ Жесткого Диска

```
sync; dd if=/dev/zero of=tempfile bs=1M count=1024; sync
```

ТЕСТ Скорости ЧТЕНИЯ Жесткого Диска

```
dd if=tempfile of=/dev/null bs=1M count=1024
```

Проверка Производительности HDD

```
yum install hdparm -y  
hdparm -Tt /dev/sda
```

Набор примеров испльзования nmap Сканировать Один Порт :

```
nmap -p 80 192.168.1.1
```

Сканировать Несколько Портов :

```
nmap -p 80,443 192.168.1.1
```

Сканировать Диапазон Портов :

```
nmap -p 80-1000 192.168.1.1
```

Сканировать несколько самых Распространенных Портов :

```
nmap --top-ports 10 192.168.1.1
```

Активировать Быстрый Режим сканирования :

```
nmap -F 192.168.1.1
```

Показать Только Открытые Порты (либо возможно открытые) :

```
nmap --open 192.168.1.1
```

Включить Определение ОС :

```
nmap -O 192.168.1.1
```

Сканирование Фаервола на Уязвимости TCP Null сканирование :

```
nmap -sN 192.168.1.1
```

TCP Fin сканирование :

```
nmap -sF 192.168.1.1
```

TCP Xmas сканирование :

```
nmap -sX 192.168.1.1
```

Сохранить результат сканирования Nmap в Текстовый Файл :

```
nmap 192.168.1.1 > output.txt
```

Пример удобного запуска виртуальной машины с помощью бат файла start.bat запускаем нашу виртуальную машину в тихом режиме

```
start c:/"Program Files"/Oracle/VirtualBox/VBoxManage startvm test.dev --type headless
```

переходим в директорию нашего проекта

```
CD d:/htdocs/test.dev
```

запускаем сборщик gulp

```
start C:/"Program Files"/Git/bin/sh.exe --login -i -e gulp
```

ждем 35 секунд пока виртуалка загрузится

```
ping -n 35 localhost > null
DEL null
```

запускаем программы

```
start c:/"Program Files (x86)"/portSoft/putty.exe -ssh test.dev
start c:/"Program Files (x86)"/Robomongo/Robomongo.exe
start c:/"Program Files (x86)"/RedisDesktopManager/rdm.exe
```

Создание бэкапа системы Создаем файл

```
nano /home/utz0r2/backup.sh
```

Записуем в него

```
#!/bin/bash
destination_folder=/home/utz0r2/backup/`date +%F`
archive_file="backup-`date +%H%M`.tar.gz"
mkdir -p $destination_folder
/bin/tar -czvf $destination_folder/$archive_file / --exclude=/proc --exclude=/dev --exclude=/home/utz0r2/backup
```

Делаем исполняемым

```
chmod +x /home/USERNAME/backup/backup.sh
```

Запускаем

```
/home/utz0r2/backup.sh
```

В /home/utz0r2/backup/дата/ будет лежать бекап.
