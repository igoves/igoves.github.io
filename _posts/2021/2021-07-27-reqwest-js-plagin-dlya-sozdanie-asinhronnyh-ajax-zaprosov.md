---
title: "reqwest - js плагин для создание асинхронных ajax запросов"
categories: 
  - "js"
---

```
reqwest('path/to/html', function (resp) {
  qwery('#content').html(resp)
})

reqwest({
    url: 'path/to/html'
  , method: 'post'
  , data: { foo: 'bar', baz: 100 }
  , success: function (resp) {
      qwery('#content').html(resp)
    }
})
```

  
[https://github.com/ded/Reqwest](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2RlZC9SZXF3ZXN0)
