---
title: "spatie/laravel-flash - легковесный пакет для флеш сообщений"
date: ""
categories: 
  - "php"
---

```
class MySpecialSnowflakeController
{
    public function store()
    {
        // …

        flash('My message', 'my-class');

        return back();
    }
}
```

```
@if(flash()->message)
    <div class="{{ flash()->class }}">
        {{ flash()->message }}
    </div>
@endif
```

  
[https://github.com/spatie/laravel-flash](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NwYXRpZS9sYXJhdmVsLWZsYXNo)
