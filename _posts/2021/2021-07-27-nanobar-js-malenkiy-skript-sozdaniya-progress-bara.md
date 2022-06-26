---
title: "nanobar js - маленький скрипт создания прогресс бара"
categories: 
  - "js"
---

![nanobar js - маленький скрипт создания прогресс бара](images/1462179304_untitled-1.jpg "nanobar js - маленький скрипт создания прогресс бара")

  
Пример  

```
var options = {
  classname: 'my-class',
  id: 'my-id',
  target: document.getElementById('myDivId')
};

var nanobar = new Nanobar( options );

// move bar
nanobar.go( 30 ); // size bar 30%
nanobar.go( 76 ); // size bar 76%

// size bar 100% and and finish
nanobar.go(100);
```

  
[http://nanobar.jacoborus.codes/](https://dev.xfor.top/go/aHR0cDovL25hbm9iYXIuamFjb2JvcnVzLmNvZGVzLw%3D%3D)
