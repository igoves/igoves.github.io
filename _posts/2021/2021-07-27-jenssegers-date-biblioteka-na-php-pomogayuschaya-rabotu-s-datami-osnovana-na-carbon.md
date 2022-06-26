---
title: "jenssegers/date - библиотека на php помогающая работу с датами основана на Carbon"
date: ""
categories: 
  - "php"
---

```
use Jenssegers\\Date\\Date;
Date::setLocale('nl');
echo Date::now()->format('l j F Y H:i:s'); // zondag 28 april 2013 21:58:16
echo Date::parse('-1 day')->diffForHumans(); // 1 dag geleden
```

  
[https://github.com/jenssegers/date](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2plbnNzZWdlcnMvZGF0ZQ%3D%3D)
