---
title: "Отправка письма в UTF-8"
date: ""
categories: 
  - "php"
tags: 
  - "mail"
---

```
function mail_utf8($to, $from, $subject, $message){    $subject = '=?UTF-8?B?' . base64_encode($subject) . '?=';     $headers  = "MIME-Version: 1.0\\r\\n";     $headers .= "Content-type: text/plain; charset=utf-8\\r\\n";    $headers .= "From: $from\\r\\n";     return mail($to, $subject, $message, $headers);} // пример использованияmail_utf8('to-user@gmail.com', 'no-reply@example.ru', 'Заголовок сообщения', 'Текст сообщения');
```
