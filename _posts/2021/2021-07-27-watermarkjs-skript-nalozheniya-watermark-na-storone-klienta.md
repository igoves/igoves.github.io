---
title: "watermark.js - скрипт наложения watermark на стороне клиента"
categories: 
  - "js"
---

![watermark.js - скрипт наложения watermark на стороне клиента](images/1432668664_1432130787_untitled-3.png "watermark.js - скрипт наложения watermark на стороне клиента")

  
Пример кода

```

// load local images
watermark(['/img/coffee.jpg', '/img/logo.png']);

// load cross domain images
watermark(['http://web.com/a.jpg', 'http://web.com/b.jpg'], function (img) {
  img.crossOrigin = 'anonymous';
});

// load a url and a file object
var upload = document.querySelector('input[type=file]').files[0];
watermark(['/img/photo.jpg', upload]);
          
```

[https://github.com/brianium/watermarkjs](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2JyaWFuaXVtL3dhdGVybWFya2pz) | [Демонстрация](https://dev.xfor.top/go/aHR0cDovL2JyaWFuaXVtLmdpdGh1Yi5pby93YXRlcm1hcmtqcy8%3D)
