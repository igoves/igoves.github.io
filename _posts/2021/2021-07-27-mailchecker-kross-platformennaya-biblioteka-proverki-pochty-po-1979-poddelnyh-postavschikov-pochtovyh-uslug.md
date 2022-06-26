---
title: "mailchecker - кросс-платформенная библиотека проверки почты по 1979 поддельных поставщиков почтовых услуг"
date: ""
categories: 
  - "php"
---

Пример использования на php

```
include __DIR__."/MailChecker/platform/php/MailChecker.php";

if(!MailChecker('myemail@yopmail.com')){
  die('O RLY !');
}

if(!MailChecker('myemail.com')){
  die('O RLY !');
}
```

  
[https://github.com/FGRibreau/mailchecker](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0ZHUmlicmVhdS9tYWlsY2hlY2tlcg%3D%3D)
