---
title: "sysend.js - скрипт передачи сообщений между вкладками одного браузера"
date: "2021-01-11"
categories: 
  - "js"
tags: 
  - "between"
  - "browser"
  - "messages"
---

```
window.onload = function() {
    sysend.on('foo', function(message) {
        console.log(message);
    });
    var input = document.getElementsByTagName('input')[0];
    document.getElementsByTagName('button')[0].onclick = function() {
        sysend.broadcast('foo', {message: input.value});
    };
};
```

[https://github.com/jcubic/sysend.js](https://github.com/jcubic/sysend.js)
