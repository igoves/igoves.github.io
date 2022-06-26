---
title: "Полупрозрачный блок"
date: "2010-05-18"
categories: 
  - "css"
tags: 
  - "blok"
  - "validno"
  - "prozrachnost"
---

Блок валидный, отображается правильно во всех последних браузерах.

```

  <style type="text/css">
    .opacity {
      margin:40px;
      padding:20px;
      background:
      url(opacity/AAAAABJR.png);
      background:rgba(0, 0, 0, 0.5);
    }
  </style>
  <!--[if lte IE 7]>
    <style type="text/css">
      .opacity {
        zoom:1;
        background:#000;
        filter:alpha(opacity=50);
      }
      .opacity * {
        position:relative;
      }
    </style>
  <![endif]-->

  <div class="opacity">
    <h1>Привет!</h1>
    <p>Это полупрозрачный блок.</p>
  </div>
```

И еще один нюанс, по моему хороший, сам блок прозрачный а шрифт нет. ДЕМО [смотреть](https://dev.xfor.top/uploads/files/demo/007/index.html)
