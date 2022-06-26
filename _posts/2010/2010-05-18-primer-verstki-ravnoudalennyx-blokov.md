---
title: "Пример верстки равноудаленных блоков"
date: "2010-05-18"
categories: 
  - "css"
tags: 
  - "blokov"
  - "verstki"
---

```
* { margin:0; padding:0;}
.container { text-align: justify; text-justify:newspaper; }
.box{ display:-moz-inline-box; display:inline-block; vertical-align:top; text-align:left; width:200px; height:200px; background:red; }
.box p{ padding:10px;}
/*IE6*/* html .box{ display:inline; }
/*IE7*/* + html .box{ display:inline; }
.under{display:-moz-inline-box; display:inline-block; width:100%; }
```

```
<div class="container">
<div class="box"><p>текст текст текст текст текст текст текст текст текст текст текст текст </p></div>
<div class="box"><p>текст текст текст текст текст текст текст текст текст текст текст текст текст </p></div>
<div class="box"><p>текст текст текст текст текст текст текст текст текст текст текст текст текст текст текст текст текст </p></div>
<div class="box"><p>текст текст текст текст текст текст текст текст текст текст текст текст текст текст </p></div>
<span class="under"></span>
</div>
```

ДЕМО: [Смотреть](https://dev.xfor.top/uploads/files/demo/008/index.html)
