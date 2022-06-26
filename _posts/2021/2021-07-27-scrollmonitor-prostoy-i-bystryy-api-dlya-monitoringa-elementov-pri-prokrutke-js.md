---
title: "scrollMonitor - простой и быстрый API для мониторинга элементов при прокрутке JS"
date: ""
categories: 
  - "js"
---

scrollMonitor позволяет получать событие когда элемент вошел или вышел из видимой области. Скрипт это делает используя объекты watcher-ы, которые следят за элементами и их триггерами событий. Watcher также включает в себя информацию про элемент за которым следит, включая видимость элемента и расположение относительно окна просмотра.  
  
Не вдаваясь в подробности скрипт спроектирован очень быстрым, на чистом [javascript](https://dev.xfor.top/tags/).  
  
Пример  

```
var scrollMonitor = require("./scrollMonitor"); // if you're not using require, you can use the scrollMonitor global.var myElement = document.getElementById("itemToWatch");var elementWatcher = scrollMonitor.create( myElement );elementWatcher.enterViewport(function() {    console.log( 'I have entered the viewport' );});elementWatcher.exitViewport(function() {    console.log( 'I have left the viewport' );});
```

  
[https://github.com/sakabako/scrollMonitor](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Nha2FiYWtvL3Njcm9sbE1vbml0b3I%3D)
