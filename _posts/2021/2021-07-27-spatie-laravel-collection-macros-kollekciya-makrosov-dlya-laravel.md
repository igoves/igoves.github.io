---
title: "spatie/laravel-collection-macros - коллекция макросов для laravel"
date: ""
categories: 
  - "php"
---

пример **after**  

```
$collection = collect([1,2,3]);

$currentItem = 2;

$currentItem = $collection->after($currentItem); // return 3;
$collection->after($currentItem); // return null;

$currentItem = $collection->after(function($item) {
    return $item > 1;
}); // return 3;
```

  
[https://github.com/spatie/laravel-collection-macros](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NwYXRpZS9sYXJhdmVsLWNvbGxlY3Rpb24tbWFjcm9z)
