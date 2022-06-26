---
title: "OxCom/constraint-validator - js валидатор форм"
date: "2020-06-17"
categories: 
  - "js"
tags: 
  - "forms"
  - "validator"
---

```
import {
    Form,
    NotBlank,
    Email,
    Length
} from 'constraint-validator';

const form = new Form();

form
    .add('email', [
        new NotBlank(),
        new Email(),
    ])
    .add('password', [
        new NotBlank(),
        new Length({min: 6}),
    ]);

const errors = form.validate({
    email: 'email@example.com',
    password: '1234567',
});

// Object with list of invalid properties. Each property contains array of errors
console.log(errors)
```

[https://github.com/OxCom/constraint-validator](https://github.com/OxCom/constraint-validator)
