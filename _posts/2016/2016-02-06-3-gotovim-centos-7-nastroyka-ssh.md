---
title: "3 - Готовим CentOS 7. Настройка ssh"
date: "2016-02-06"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/t7CRUj--EUQ?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

 Открываем конфиг

```
nano /etc/ssh/sshd_config
```

Используем не стандартный порт

Port 2222

Запрещаем использовать протокол 1

Protocol 2

Запрещаем логинится от рута, обычно брутят рута по стандартому порту, поэтому мы это изменим

PermitRootLogin no

Разрешаем логинится из ssh только определенному юзеру мне utz0r2

AllowUsers utz0r2

Запускаем semanage

```
yum -y install policycoreutils-python
semanage port -a -t ssh_port_t -p tcp 2222
```

Перезапускаем sshd

```
service sshd restart
```

Проверяем

```
service sshd status
nmap 127.0.0.1	
```

или так

```
netstat -tulpn
```

В дальнейшем будем пользоваться только ssh через программу putty Пробрасываем порты в нашей виртуальной машине 22 -> 2222, 80 -> 80 Прописуем в нашей windows машине в \\\\WINDOWS\\\\system32\\\\drivers\\\\etc\\\\hosts

192.168.56.1 test.dev

Предаварительно узнав внешний айпи нашей виртуальной машины (Панель управления\\\\Сеть и Интернет\\\\Сетевые подключения) Все готово для дальнейшей работы c сервером через ssh.
