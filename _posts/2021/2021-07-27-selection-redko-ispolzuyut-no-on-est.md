---
title: "Selection редко используют, но он есть..."
categories: 
  - "css"
tags: 
  - "css"
  - "selection"
---

Selection не поддержует ИЕ (как обычно).  

![Selection редко используют, но он есть...](images/1274697540_bezimeni-1.jpg "Selection редко используют, но он есть...")

  
Синтаксис:  

```
::-moz-selection{    background:#cc0000;    color:#fff;}::selection {    background:#cc0000;    color:#fff;}code::-moz-selection {    background: #333333;}code::selection {    background: #333333;}
```

  
Обалденная [ДЕМКА](https://dev.xfor.top/go/aHR0cDovL2ZpY2h0cmUubmV0L3lvcC5odG1s) (выделите текст)
