---
title: "Freezeframe.js - библиотека приостанавливает анимированные файлы .gifs и возвращает им анимирацию при наведении мыши / щелчке мыши / касании или запуске вручную"
categories: 
  - "js"
---

Работает это так: записывается первый кадр в canvas элемент. После старта проигрывается сама GIF  

```
// Default options
new Freezeframe();

// String as selector
new Freezeframe('.foo');

// DOM reference as selector
new Freezeframe(document.querySelectorAll('.foo'));

// Custom options
new Freezeframe({
  selector: '.foo',
  trigger: 'click',
  overlay: true,
  responsive: false
});

// Also valid syntax
new Freezeframe('.foo', {
  trigger: 'click',
  overlay: true,
  responsive: false
});
```

  
[https://github.com/ctrl-freaks/freezeframe.js/](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2N0cmwtZnJlYWtzL2ZyZWV6ZWZyYW1lLmpzLw%3D%3D)
