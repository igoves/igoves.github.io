---
title: "cachearium - продвинутая система кэширования на PHP"
date: ""
categories: 
  - "php"
---

Пример  

```
$data = 'xxxx';

// store
$cache = CacheAbstract::factory('your backend');
$cache->store($data, new CacheKey('Namespace', 'Subname'));

// get it later
try { 
    $data2 = $cache->get(new CacheKey('Namespace', 'Subname'));
    // $data2 == 'xxxx';
}
catch (NotCachedException($e)) {
    // handle not cached
}

// store new value with automatic invalidation
$data = 'yyy';
$cache->store($data, new CacheKey('Namespace', 'Subname'));
```

  
[https://github.com/Corollarium/cachearium](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0Nvcm9sbGFyaXVtL2NhY2hlYXJpdW0%3D)
