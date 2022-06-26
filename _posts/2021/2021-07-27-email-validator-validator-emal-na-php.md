---
title: "email-validator - валидатор emal на PHP"
categories: 
  - "php"
---

Маленький php скрипт для валидации email адресов.  
Проверяет присутствие example в домене, одноразовых почтовых сервисов типа mailinator.com, проверяет на наличие role-based адресов типа abuse@, и проверяет MX records.  

```
$validator = new \\EmailValidator\\Validator();

$validator->isValid('example@google.com');              // true
$validator->isValid('abuse@google.com');                // false
$validator->isValid('example@example.com');             // false
```

  
[https://github.com/nojacko/email-validator](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL25vamFja28vZW1haWwtdmFsaWRhdG9y)
