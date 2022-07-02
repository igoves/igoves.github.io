---
title: "Установка Redis на Ubuntu c PHP"
categories: 
  - "note"
---

```
sudo add-apt-repository ppa:chris-lea/redis-server
sudo apt-get update
sudo apt-get install redis-server
sudo apt-get install php5-redis
```

  
Проверяем  

```
redis-cli ping
```

В ответ должны получить **PONG**  
  
В php.ini прописываем ( наши сессии теперь будут храниться в redis)  

```
session.save_handler = redis
session.save_path    = tcp://127.0.0.1:6379
# если с паролем то
# session.save_path = "tcp://127.0.0.1:6379?auth=yourverycomplexpasswordhere"
```

или прямо в файле php  

```
ini_set('session.save_handler', 'redis');
ini_set('session.save_path',    'tcp://127.0.0.1:6379');
```

  
в /etc/redis/redis.conf прописываем пароль  

```
requirepass yourverycomplexpasswordhere
```

  
Перегружаем  

```
sudo service php5-fpm restart 
sudo service redis-server restart
```

  
Конектимся  

```
redis-cli -h 127.0.0.1
```

  
Командой смотрим что зак ключи есть в нашей бд  

keys \*

в ответ получаем  

(error) NOAUTH Authentication required.

  
Что значит нам нужно авторизироваться для начала  

```
AUTH yourverycomplexpasswordhere
```

после командой  

```
keys *
```

видим пусто, либо увидим созданную сессию, что-то вроде этого  

\\"PHPREDIS\_SESSION:j9rsgtde6st2rqb6lu5u6f4h83\\"

  
Документация php+redis [https://github.com/phpredis/phpredis](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BocHJlZGlzL3BocHJlZGlz) и [http://www.tutorialspoint.com/redis/](https://dev.xfor.top/go/aHR0cDovL3d3dy50dXRvcmlhbHNwb2ludC5jb20vcmVkaXMv)  
GUI Redis [http://redisdesktop.com/](https://dev.xfor.top/go/aHR0cDovL3JlZGlzZGVza3RvcC5jb20v)  
Либы на php для redis [http://redis.io/clients#php](https://dev.xfor.top/go/aHR0cDovL3JlZGlzLmlvL2NsaWVudHMjcGhw)
