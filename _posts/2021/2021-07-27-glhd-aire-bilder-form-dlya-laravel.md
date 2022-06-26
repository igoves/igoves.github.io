---
title: "glhd/aire - билдер форм для Laravel"
categories: 
  - "php"
tags: 
  - "builder"
  - "form"
  - "laravel"
---

Пример создания формы

```
{{ Aire::open()
  ->route('users.update')
  ->bind($user) }}

<div class="flex flex-col md:flex-row">

  {{ Aire::input('given_name', 'First/Given Name')
    ->id('given_name')
    ->autoComplete('off')
    ->groupClass('flex-1 mr-2') }}
    
  {{ Aire::input('family_name', 'Last/Family Name')
    ->id('family_name')
    ->autoComplete('off')
    ->groupClass('flex-1') }}
  
</div>
  
{{ Aire::email('email', 'Email Address') }}
  
{{ Aire::submit('Update User') }}
  
{{ Aire::close() }}
```

  
[https://github.com/glhd/aire](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2dsaGQvYWlyZQ%3D%3D)
