---
title: "php-buffer - php скрипт чтения или создания бинарных данных"
categories: 
  - "php"
---

Пример: инициализировать буфер в виде потока ресурса  

```
$fp = fopen('php://temp', 'w+b');
// или
$buffer = new \\Nelexa\\ResourceBuffer($fp);
```

  
[https://github.com/Ne-Lexa/php-buffer](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL05lLUxleGEvcGhwLWJ1ZmZlcg%3D%3D)
