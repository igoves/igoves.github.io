---
title: "palladium - пхп компонент для регистрации и авторизации"
date: ""
categories: 
  - "php"
---

Работает на пхп 7+ и pdo  
Включает в себя 4 компоненты: Registration, Identification, Search and Recovery  
Пример регистрация

```
<?php

$registration = new \\Palladium\\Service\\Registration($factory, $logger);

$identity = $registration->createEmailIdentity('foo@bar.com', 'password');
$registration->bindAccountToIdentity($accountId, $identity);
```

  
[https://github.com/teresko/palladium](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3RlcmVza28vcGFsbGFkaXVt)
