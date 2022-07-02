---
title: "nickdeny / darkmode-js - автоматически определяет время пользователя и переключает тему"
date: "2020-06-09"
categories: 
  - "js"
tags: 
  - "darkmode"
  - "switcher"
---

Облегченный и кросс-браузерный скрипт поможет вам автоматически определять время пользователя и переключать тему на темную. Кроме того, он весит всего 2,39 КБ (1.05 КБ в сжатом виде) и написан на чистом Javascript, без каких-либо плагинов и jQuery!

```
<script src="darkmode.js"></script>
<script>
  var options = {
    light: "light.css",
    dark: "dark.css",
    startAt: "23:00",
    endAt: "06:00",
    checkSystemScheme: true,
    saveOnToggle: true
  };
  var DarkMode = new DarkMode(options);
</script>
```

[https://github.com/nickdeny/darkmode-js](https://github.com/nickdeny/darkmode-js)
