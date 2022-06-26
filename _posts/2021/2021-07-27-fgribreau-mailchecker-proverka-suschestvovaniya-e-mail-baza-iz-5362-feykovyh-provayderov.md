---
title: "FGRibreau/mailchecker - проверка существования e-mail, база из 5362 фейковых провайдеров"
date: ""
categories: 
  - "php"
---

```
include __DIR__."/MailChecker/platform/php/MailChecker.php";

if(!MailChecker::isValid('myemail@yopmail.com')){
  die('O RLY !');
}

if(!MailChecker::isValid('myemail.com')){
  die('O RLY !');
}
```

  
[https://github.com/FGRibreau/mailchecker#php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0ZHUmlicmVhdS9tYWlsY2hlY2tlciNwaHA%3D)
