---
title: "2 - Готовим CentOS 7. Основные действия после установки"
date: "2016-02-05"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/nLapnYQIqIM?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

 Обновиться

```
yum -y update && yum -y upgrade
```

Установим программы wget, nano, mc, nmap,

```
yum install wget nano mc nmap -y
```

Выставим имя хоста

```
echo $HOSTNAME
nano /etc/hostname
```

Посмотрим какие порты открыты

```
nmap 127.0.0.1	
```

ssh - 22 окрыт, значит устанавливать его не надо, только настроить. Об этом будет позже)
