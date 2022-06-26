---
title: "Egg.js - скрипт создания пасхалок для сайта"
categories: 
  - "js"
---

Пример использования

```
var egg = new Egg();
egg
  .addCode("up,up,down,down,left,right,left,right,b,a", function() {
    jQuery('#egggif').fadeIn(500, function() {
      window.setTimeout(function() { jQuery('#egggif').hide(); }, 5000);
    }, "konami-code");
  })
  .addHook(function(){
    console.log("Hook called for: " + this.activeEgg.keys);
    console.log(this.activeEgg.metadata);
  })
  .listen();
```

  
[https://github.com/mikeflynn/egg.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21pa2VmbHlubi9lZ2cuanM%3D) / [Демка](https://dev.xfor.top/go/aHR0cDovL3RoYXRtaWtlZmx5bm4uY29tL2VnZy5qcy8%3D) ( нажмите up,up,down,down,left,right,left,right,b,a )
