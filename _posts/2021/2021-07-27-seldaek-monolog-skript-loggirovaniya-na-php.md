---
title: "Seldaek/monolog - скрипт логгирования на PHP"
categories: 
  - "php"
---

Отправляйте свои логи в файлы, на почту, в базу, по сокетам и другим веб сервисам.  
Пример использования:  

```
<?php

use Monolog\\Logger;
use Monolog\\Handler\\StreamHandler;

// create a log channel
$log = new Logger('name');
$log->pushHandler(new StreamHandler('path/to/your.log', Logger::WARNING));

// add records to the log
$log->warning('Foo');
$log->error('Bar');
```

  
[https://github.com/Seldaek/monolog](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1NlbGRhZWsvbW9ub2xvZw%3D%3D)
