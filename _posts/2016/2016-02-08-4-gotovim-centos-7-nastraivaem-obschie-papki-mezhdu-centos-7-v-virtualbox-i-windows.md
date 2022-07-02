---
title: "4 - Готовим CentOS 7. Настраиваем общие папки между CentOS 7 в virtualbox и windows"
date: "2016-02-08"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/3aEhBV8qBWE?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

 В нашей системе(виндовс) создаем общую папку test.dev в нее ложим файлик 1.php с содержимым устройства -> подключить образ диска Дополнительной гостевой ос - устанавливаем дополнительные пакеты

```
yum install gcc make kernel-devel-$(uname -r) bzip2 -y
```

\- монтируем привод

```
mount /dev/cdrom /mnt
```

\- и запускаем VboxLinuxAdditions.run

```
cd /mnt && sudo sh ./VBoxLinuxAdditions.run
```

Если у вас вылезла ошибка, как у меня **Building the OpenGL support module\[FAILED\]** То выполняем команду

```
export MAKE='/usr/bin/gmake -i'
```

И запустим опять

```
./VBoxLinuxAdditions.run
```

Проверяем наличие vboxsf

```
modprobe vboxsf
```

Ошибки не выскочило значит все пока что хорошо. Создаем папку в системе CentOS которая будет у нас общей с виндовс

```
mkdir -p /var/www/test.dev
```

Монтируем общую папку

```
mount -t vboxsf test.dev /var/www/test.dev
```

Проверяем что в нашей папке test.dev теперь лежить наш созданный в виндовсе файл 1.php

```
ls /var/www/test.dev/
```

Если видим файлы нашего проекта, то все хорошо и можно добавить это монтирование в загрузку

```
nano -w /etc/rc.local 
```

Дописываем:

```
modprobe vboxsf
mount -t vboxsf test.dev /var/www/test.dev
```

Выполняем

```
chmod +x /etc/rc.d/rc.local
```

Теперь общая папка у нас есть и будет подключаться автоматом при загрузке системы.
