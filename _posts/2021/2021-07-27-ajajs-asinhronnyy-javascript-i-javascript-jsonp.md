---
title: "aja.js - асинхронный JavaScript и JavaScript/JSON(P)"
categories: 
  - "js"
---

Пример  

```
aja()  .method('get')  .url('/api/customer')  .data({firstname: 'john romuald'})  .on('200', function(response){      //well done  })  .go();aja()  .method('put')  .url('/api/customer')  .cache(false)  .body({id : 12, firstname: 'john romuald', job : 'linguist'})  .on('200', function(response){      //well done  })   .on('40*', function(response){      //something is definitely wrong  })  .on('500', function(response){      //oh crap  })  .go();
```

  
[https://github.com/krampstudio/aja.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2tyYW1wc3R1ZGlvL2FqYS5qcw%3D%3D)
