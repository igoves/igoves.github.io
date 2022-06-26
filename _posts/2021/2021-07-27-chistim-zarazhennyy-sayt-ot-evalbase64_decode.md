---
title: "Чистим зараженный сайт от eval(base64_decode())"
date: ""
categories: 
  - "note"
tags: 
  - "base64_decode"
---

![Чистим зараженный сайт от eval(base64_decode())](images/1333791622_49.jpg "Чистим зараженный сайт от eval(base64_decode())")

  
Получаем список зараженных файлов  

```
$find . -print0 -name "*.php" | xargs -0 grep -l "eval(base64_decode"
```

  
  
Лечим файлы ( вырезает eval(base64\_decode(труляля)); )  

```
$find . \\( -name "*.php" \\) -exec grep -Hn "[\\t]*eval(base64_decode(.*));" {} \\; -exec sed -i 's/[\\t]*eval(base64_decode(.*));//g' {} \\;
```
