---
title: "string - библиотека для манипуляции с multibyte strings"
date: ""
categories: 
  - "php"
---

```
use Opis\\String\\UnicodeString as wstring;

$str = wstring::from('??????????');

echo $str->substring(3, 4)
         ->toUpper(); //> ????
```

  
[https://github.com/opis/string](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL29waXMvc3RyaW5n)
