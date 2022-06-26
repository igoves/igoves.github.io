---
title: "EmailValidator - php валидатор e-mail"
date: ""
categories: 
  - "php"
---

```
<?php

use Egulias\\EmailValidator\\EmailValidator;

$validator = new EmailValidator();
$validator->isValid("example@example.com", new RFCValidation()); //true
```

  
[https://github.com/egulias/emailvalidator](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2VndWxpYXMvZW1haWx2YWxpZGF0b3I%3D)
