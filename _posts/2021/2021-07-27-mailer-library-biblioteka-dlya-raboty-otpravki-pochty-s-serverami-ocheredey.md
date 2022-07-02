---
title: "mailer-library - библиотека для работы отправки почты с серверами очередей"
categories: 
  - "php"
---

Поддерживает: Beanstalkd Backend, Pdo Backend, RabbitMq Backend, Redis Backend, SQS Backend  
Пример для Beanstalkd  
Добавить в очередь

```
use Da\\Mailer\\Model\\MailMessage;
use Da\\Mailer\\Queue\\MailQueue;
use Da\\Mailer\\Queue\\Backend\\Beanstalkd\\BeanstalkdMailJob;
use Da\\Mailer\\Queue\\Backend\\Beanstalkd\\BeanstalkdQueueStoreAdapter;
use Da\\Mailer\\Queue\\Backend\\Beanstalkd\\BeanstalkdQueueStoreConnection;
use PDO;

$message = new MailMessage([
    'from' => 'sarah.connor@gmail.com',
    'to' => 'john.connor@gmail.com',
    'subject' => 'What is up?',
]);

$conn = new BeanstalkdQueueStoreConnection([
    'host' => 'localhost',
    'port' => 'root']);

$adapter = new BeanstalkdQueueStoreAdapter($conn);

$queue = new MailQueue($adapter);

$job = new BeanstalkdMailJob([
    'message' => json_encode($message),
]);

if (!$queue->enqueue($job)) {
    // ... queue operation failed
}
```

  
Забираем из очереди

```
use Da\\Mailer\\Queue\\MailQueue;
use Da\\Mailer\\Queue\\Backend\\Beanstalkd\\BeanstalkdQueueStoreAdapter;
use Da\\Mailer\\Queue\\Backend\\Beanstalkd\\BeanstalkdQueueStoreConnection;

$conn = new BeanstalkdQueueStoreConnection([
    'connectionString' => 'mysql:host=localhost;dbname=test',
    'username' => 'root',
    'password' => 'password'
], [PDO::ATTR_PERSISTENT => true]);

$adapter = new BeanstalkdQueueStoreAdapter($conn);

$queue = new MailQueue($adapter);

if (($job = $queue->dequeue()) !== null) {
    // ... do something with received job
    // ... send it using `mail()` function for example 
    // ... or by using MailMessageWorker 

    $job->markAsCompleted();
    $queue->ack($job);
}
```

  
[https://github.com/2amigos/mailer-library](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tLzJhbWlnb3MvbWFpbGVyLWxpYnJhcnk%3D)
