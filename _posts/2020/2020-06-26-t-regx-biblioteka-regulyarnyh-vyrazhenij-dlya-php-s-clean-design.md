---
title: "T-Regx - библиотека регулярных выражений для PHP с Clean Design"
date: "2020-06-26"
categories: 
  - "php"
tags: 
  - "design"
  - "regex"
---

```
pattern('\d{3}')->match('My phone is 456-232-123')->first();  // '456'
pattern('\d{3}')->match('My phone is 456-232-123')->all();    // ['456', '232', '123']
pattern('\d{3}')->match('My phone is 456-232-123')->only(2);  // ['456', '232']
```

[https://github.com/T-Regx/T-Regx](https://github.com/T-Regx/T-Regx)
