---
title: "1 - Готовим CentOS 7. Запускаем сеть после установки"
date: "2016-01-20"
categories: 
  - "note"
tags: 
  - "centos"
  - "net"
  - "ping"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/M-TpeSf3CQ4?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

```
ping ya.ru
nmcli d
```

Видим инет не доступен. Запускаем

```
nmtui
```

выставим **x Automaticlly connect**

Перезапускаем

```
service network restart
```

Проверяем

```
pint ya.ru
```
