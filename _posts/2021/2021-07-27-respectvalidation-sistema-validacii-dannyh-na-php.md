---
title: "Respect\\Validation - система валидации данных на PHP"
date: ""
categories: 
  - "php"
---

Простые правила для валидации

```
v::numeric()->positive()->between(1, 256)->validate($myNumber)
```

  
Контроль детализации для продвинутой отчетности.  
Почти 100 проверок.  
Работает на PHP 5.3+ или HHVM 3.3+  
  
Пример простой валидации

```
$number = 123;
v::numeric()->validate($number); //true
```

  
[http://respect.li/Validation/](https://dev.xfor.top/go/aHR0cDovL3Jlc3BlY3QubGkvVmFsaWRhdGlvbi8%3D)
