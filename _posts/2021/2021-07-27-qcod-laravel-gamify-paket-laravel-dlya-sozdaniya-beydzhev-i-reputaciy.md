---
title: "qcod/laravel-gamify - пакет laravel для создания бейджев и репутаций"
categories: 
  - "php"
---

```
$user = $request->user();
$post = $user->posts()->create($request->only(['title', 'body']));

$user->givePoint(new PostCreated($post));

// get integer point
$user->getPoints(); // 20

// formatted result
$user->getPoints(true); // if point is more than 1000 1K+
```

  
[https://github.com/qcod/laravel-gamify](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Fjb2QvbGFyYXZlbC1nYW1pZnk%3D)
