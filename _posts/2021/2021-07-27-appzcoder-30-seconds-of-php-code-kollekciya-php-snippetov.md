---
title: "appzcoder/30-seconds-of-php-code - коллекция php сниппетов"
categories: 
  - "php"
---

Короткие функции: all, any, chunk, deepFlatten, drop, findLast, findLastIndex, flatten, groupBy, hasDuplicates, head, last, pluck, pull, reject, remove, tail, take, without, average, factorial, fibonacci, gcd, isEven, isPrime, lcm, median, endsWith, firstStringBetween, isAnagram, isLowerCase, isUpperCase, palindrome, startsWith и др.  
  
Пример, получение последнего элемента массива:  

```
function findLast($items, $func)
{
    $filteredItems = array_filter($items, $func);
    return array_pop($filteredItems);
}
```

  
[https://github.com/appzcoder/30-seconds-of-php-code](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2FwcHpjb2Rlci8zMC1zZWNvbmRzLW9mLXBocC1jb2Rl)
