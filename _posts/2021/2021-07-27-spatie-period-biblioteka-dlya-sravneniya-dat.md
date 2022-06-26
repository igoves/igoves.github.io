---
title: "spatie/period - библиотека для сравнения дат"
date: ""
categories: 
  - "php"
---

Пример использования, найти общие  

```
/*
 * A       [========]
 * B                    [==]
 * C                            [=====]
 * CURRENT        [===============]
 *
 * OVERLAP        [=]   [==]    [=]
 */
 
$a = Period::make('2018-01-01', '2018-01-31');
$b = Period::make('2018-02-10', '2018-02-20');
$c = Period::make('2018-03-01', '2018-03-31');

$current = Period::make('2018-01-20', '2018-03-10');

$overlaps = $current->overlap($a, $b, $c); 
```

  
[https://github.com/spatie/period](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NwYXRpZS9wZXJpb2Q%3D)
