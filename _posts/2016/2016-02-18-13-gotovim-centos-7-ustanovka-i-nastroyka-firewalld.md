---
title: "13 - Готовим CentOS 7. Установка и настройка firewalld"
date: "2016-02-18"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/c1NxM7iYnXA?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

Установка

```
yum -y install firewalld
```

Запуск

```
systemctl start firewalld
```

Статус

```
systemctl status firewalld
```

**Зоны** - **drop** – входящие сетевые пакеты сбрасываются, без ответа, допускаются только исходящие соединения - **block** – входящие сетевые соединения отклоняются с сообщением icmp-host-prohibited, допускаются только сетевые соединения инициированные внутри нашей системы. - **public** – при недоверии к компьютерам, разрешается устанавливать только конкретные входящие соединения. - **external** – для использования во внешних сетях с разрешенным маскарадингом, особенно для роутеров, разрешается устанавливать только конкретные входящие соединения - **dmz** – для компьютеров собственной demilitarized zone которые публично доступны с ограниченным доступом к нашей внутренней сети, разрешается устанавливать только конкретные входящие соединения. - **work/home/internal** – максимальное доверие к компьютерам, уверенность в том, что они не приченят вреда нашему компьютеру, разрешается устанавливать только конкретные входящие соединения - **trusted** – все сетевые соединения разрешены.

Посмотреть текущую зону

```
firewall-cmd --get-default-zone
```

Для смены зоны например на home

```
firewall-cmd --set-default-zone=home
```

Либо непосредсвтенно в конфиге

```
nano /etc/firewalld/firewalld.conf
```

Получить текущую конфигурацию для нашей зоны public

```
firewall-cmd --zone=public --list-all	
```

После внесение изменений перезагрузить FirewallD можно так

```
firewall-cmd --reload	
```

режим паники, блокирующий все сетевые соединения

```
firewall-cmd --panic-on	
```

отмена режима паники

```
firewall-cmd --panic-off	
```

добавить порт к зоне

```
firewall-cmd [--zone=] --add-port=[-]/ [--timeout=]
```

удалить порт из зоны

```
firewall-cmd [--zone=] --remove-port=[-]/ [--timeout=]
```

Добавим 80 порт в доверенные

```
firewall-cmd --permanent --add-port=80/tcp
```

Посмотреть список сервисов

```
firewall-cmd --list-services
```

Добавим ssh в доверенные

```
firewall-cmd --permanent --add-port=2222/tcp
```

```
firewall-cmd --reload	
```

Посмотрим что получилось

```
firewall-cmd --list-all	
```

Ставим в автозагрузку

```
systemctl enable firewalld
```

Вот в принципе и все, пока нам нужен только 80 порт (отображается сайт) и 2222 (наш ssh). Ко всем гуи типа робомонго конектитмся через ssh тунель.
