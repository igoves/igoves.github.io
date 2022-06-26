---
title: "rennokki/befriended - laravel пакет friendship модели (фоловинг блок лайки и фильтр контента)"
categories: 
  - "php"
tags: 
  - "eloquent"
  - "laravel"
  - "php"
---

```
$bob = User::where('username', 'john')->first();
$alice = User::where('username', 'alice')->first();

User::filterFollowingsOf($bob)->get(); // You will get no results.
User::filterUnfollowingsOf($bob)->get(); // You will get Alice.

$bob->follow($alice);
User::filterFollowingsOf($bob)->get(); // You will get Alice as result.
```

  
[https://github.com/rennokki/befriended](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Jlbm5va2tpL2JlZnJpZW5kZWQ%3D)
