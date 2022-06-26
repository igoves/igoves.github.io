---
title: "Закрыть сайт с помощью cookie"
date: ""
categories: 
  - "php"
tags: 
  - "cookie"
---

```
$c = $_COOKIE['access'];if (md5($c) != "6c29cd347ef113464ffaef9d6af64fa3") die();
```

  
Нет куки у которго хэш 6c29cd347ef113464ffaef9d6af64fa3, значит вырубить дальнейшее выполнение скрипта.
