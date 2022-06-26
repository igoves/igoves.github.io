---
title: "EFTEC/BladeOne - шаблонизатор Blade одним файлом без зависимостей"
date: ""
categories: 
  - "php"
---

```
<select>
    @foreach($countries as $c)
        <option value={{$c->value}} >{{echo html_entities($c->text)}}</option>
    @nextforeach
</select>
```

  
[https://github.com/EFTEC/BladeOne](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0VGVEVDL0JsYWRlT25l)
