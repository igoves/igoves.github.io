---
title: "omnimail - php интерфейс для работы с сервисами отправки писем"
categories: 
  - "php"
---

В текущий момент поддерживает такие провайдеры: AmazonSES, Mailgun, Mailjet, Mandrill, Postmark, Sendgrid, SendinBlue  
Пример использования  

```
use Omnimail\\Email;
use Omnimail\\AmazonSES;

$sender = new AmazonSES($accessKey, $secretKey);

$email = (new Email())
    ->addTo('example@email.com')
    ->setFrom('example@email.com')
    ->setSubject('Hello, world!')
    ->setTextBody('Hello World! How are you?');

$sender->send($email);
```

  
[https://github.com/gabrielbull/omnimail](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2dhYnJpZWxidWxsL29tbmltYWls)
