---
title: "anlutro/laravel-settings - сохранение настроек в бд laravel"
categories: 
  - "php"
---

```
<?php
Setting::set('foo', 'bar');
Setting::get('foo', 'default value');
Setting::get('nested.element');
Setting::forget('foo');
$settings = Setting::all();
?>
```

  
[https://github.com/anlutro/laravel-settings](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2FubHV0cm8vbGFyYXZlbC1zZXR0aW5ncw%3D%3D)
