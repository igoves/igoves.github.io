---
title: "php-redis-react - клиент для асинхронной работы с redis"
date: ""
categories: 
  - "php"
---

Пример кода

```
$loop = React\\EventLoop\\Factory::create();
$factory = new Factory($loop);

$factory->createClient('localhost:6379')->then(function (Client $client) use ($loop) {
    $client->set('greeting', 'Hello world');
    $client->append('greeting', '!');

    $client->get('greeting')->then(function ($greeting) {
        // Hello world!
        echo $greeting . PHP_EOL;
    });

    $client->incr('invocation')->then(function ($n) {
        echo 'This is invocation #' . $n . PHP_EOL;
    });

    // end connection once all pending requests have been resolved
    $client->end();
});

$loop->run();
```

  
[https://github.com/clue/php-redis-react](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2NsdWUvcGhwLXJlZGlzLXJlYWN0)
