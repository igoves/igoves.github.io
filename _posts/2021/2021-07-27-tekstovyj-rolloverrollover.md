---
title: "Текстовый ролловер(rollover)"
date: ""
categories: 
  - "css"
---

Очень просто реализовать текстовый ролловер(rollover):  

```
<a href="#">Не активная<span>Активная</span></a>
```

  

```
a {     display:block;     width:100px;    background:#F2F2F2;     border:1px solid #DDDDDD;    font-size:14px;     line-height:26px;     color:#000000;     text-decoration:none;    text-align:center;}a:hover {     text-indent:-999em;     position:relative;}a span{     display:none;}a:hover span{    text-indent:0;     display:block;     position:absolute;     top:0;     left:0;     right:0;}
```

  
Вот и все. Демо [Текстовый ролловер](https://dev.xfor.top/uploads/files/demo/004/index.html)
