---
title: "Pawl - асинхронный вебсокет клиент на PHP"
date: ""
categories: 
  - "php"
---

**Пример** - соединяется с сервером, отправляет сообщение, выводит, закрывает соединение  

```
<?php

    require __DIR__ . '/vendor/autoload.php';

    \\Ratchet\\Client\\connect('ws://echo.socketo.me:9000')->then(function($conn) {
        $conn->on('message', function($msg) use ($conn) {
            echo "Received: {$msg}\\n";
            $conn->close();
        });

        $conn->send('Hello World!');
    }, function ($e) {
        echo "Could not connect: {$e->getMessage()}\\n";
    });
```
