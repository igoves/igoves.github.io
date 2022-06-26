---
title: "pageres - npm пакет создания скриншетов на разных экранах"
categories: 
  - "js"
---

![pageres - npm пакет создания скриншетов на разных экранах](images/1429269609_promo.jpg "pageres - npm пакет создания скриншетов на разных экранах")

  
Примеры использования

```
# Basic multi-url, multi-resolution usagepageres todomvc.com yeoman.io 1366x768 1600x900# Override outer option within grouppageres [ yeoman.io 1366x768 1600x900 --no-crop ] [ todomvc.com 1024x768 480x320 ] --crop# Provide a custom filename templatepageres todomvc.com 1024x768 --filename '<%= date %> - <%= url %>'# Capture a specific elementpageres yeoman.io 1366x768 --selector '.page-header'# Hide a specific elementpageres yeoman.io 1366x768 --hide '.page-header'# Delay and pipe in a list of urlspageres --delay 3 1366x768 < urls.txt# Capture a local filepageres unicorn.html 1366x768# Pipe in resolutionscat screen-resolutions.txt | pageres todomvc.com yeoman.io
```

  
Есть так же плагин под грант grunt-pageres  
[https://github.com/sindresorhus/pageres](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NpbmRyZXNvcmh1cy9wYWdlcmVz)
