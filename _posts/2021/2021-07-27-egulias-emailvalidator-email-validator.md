---
title: "egulias/emailvalidator - email валидатор"
categories: 
  - "php"
---

Поддерживает такие проверки:  
\- RFCValidation  
\- NoRFCWarningsValidation  
\- DNSCheckValidation  
\- SpoofCheckValidation  
\- MultipleValidationWithAnd  
\- Ваша собственная валидация  

```
<?php

use Egulias\\EmailValidator\\EmailValidator;
use Egulias\\EmailValidator\\Validation\\DNSCheckValidation;
use Egulias\\EmailValidator\\Validation\\MultipleValidationWithAnd;
use Egulias\\EmailValidator\\Validation\\RFCValidation;

$validator = new EmailValidator();
$multipleValidations = new MultipleValidationWithAnd([
    new RFCValidation(),
    new DNSCheckValidation()
]);
$validator->isValid("example@example.com", $multipleValidations); //true
```

  
[https://github.com/egulias/emailvalidator](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2VndWxpYXMvZW1haWx2YWxpZGF0b3I%3D)
