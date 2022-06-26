---
title: "RoadRunner - высокопроизводительный сервер приложений PHP, балансировщик нагрузки и менеджер процессов, написанный на Golang"
date: "2020-07-11"
categories: 
  - "go"
  - "php"
tags: 
  - "app"
  - "server"
---

```
<?php
// worker.php
ini_set('display_errors', 'stderr');
include "vendor/autoload.php";

$relay = new Spiral\Goridge\StreamRelay(STDIN, STDOUT);
$psr7 = new Spiral\RoadRunner\PSR7Client(new Spiral\RoadRunner\Worker($relay));

while ($req = $psr7->acceptRequest()) {
    try {
        $resp = new \Zend\Diactoros\Response();
        $resp->getBody()->write("hello world");

        $psr7->respond($resp);
    } catch (\Throwable $e) {
        $psr7->getWorker()->error((string)$e);
    }
}
```

[https://github.com/spiral/roadrunner](https://github.com/spiral/roadrunner)
