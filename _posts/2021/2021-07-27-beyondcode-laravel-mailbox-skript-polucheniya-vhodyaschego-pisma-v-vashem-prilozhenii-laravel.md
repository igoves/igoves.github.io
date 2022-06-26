---
title: "beyondcode/laravel-mailbox - скрипт получения входящего письма в вашем приложении Laravel"
date: ""
categories: 
  - "php"
tags: 
  - "catch"
  - "laravel"
  - "mail"
---

```
Mailbox::from('{username}@gmail.com', function (InboundEmail $email, $username) {
    // Access email attributes and content
    $subject = $email->subject();
    
    $email->reply(new ReplyMailable);
});
```

  
Поддерживает Mailgun, Postmark, SendGrid и локальный log driver  
[https://github.com/beyondcode/laravel-mailbox](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2JleW9uZGNvZGUvbGFyYXZlbC1tYWlsYm94)
