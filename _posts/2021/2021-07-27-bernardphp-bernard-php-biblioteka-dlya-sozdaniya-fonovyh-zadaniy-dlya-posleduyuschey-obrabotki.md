---
title: "bernardphp/bernard - PHP-библиотека для создания фоновых заданий для последующей обработки"
date: ""
categories: 
  - "php"
---

Поддерживает  
\- Predis / PhpRedis  
\-Amazon SQS  
\- Iron MQ  
\- Doctrine DBAL  
\- Pheanstalk  
\- PhpAmqp / RabbitMQ  
\- Queue interop  

```
<?php

use Bernard\\Driver\\Predis\\Driver;
use Predis\\Client;

$predis = new Client('tcp://localhost', array(
    'prefix' => 'bernard:',
));

$driver = new Driver($predis);
```

Запуск  

```
$ php ./example/predis.php consume
$ php ./example/predis.php produce
```

  
[https://github.com/bernardphp/bernard](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2Jlcm5hcmRwaHAvYmVybmFyZA%3D%3D)
