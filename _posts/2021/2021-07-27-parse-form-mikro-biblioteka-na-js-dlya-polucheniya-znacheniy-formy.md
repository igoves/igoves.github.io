---
title: "parse-form - микро библиотека на js для получения значений формы"
categories: 
  - "js"
---

Например есть

```
<form id='new-user-form'>    <input type="text"     name="email">    <input type="text"     name="username">    <input type="password" name="password">    <input type="submit" value="Create User"></form>
```

то определить данные формы можно с помощью это кода:

```
var form = new ParseForm('#new-user-form');form.name      ==  'John Doe'form.email     ==  'john@gmail.com'form.password  ==  'password1'
```

  
[https://github.com/AdamBrodzinski/parse-form](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0FkYW1Ccm9kemluc2tpL3BhcnNlLWZvcm0%3D)
