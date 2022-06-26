---
title: "Штуки в CSS3 о которых вы может быть не знали..."
categories: 
  - "css"
---

![Штуки в CSS3 о которых вы может быть не знали...](images/1322477145_104.jpg "Штуки в CSS3 о которых вы может быть не знали...")

  
**Несколько бекграундов:**

```
#multi-bg {    background: url(images/bg-cake.gif) center center no-repeat, url(images/bg-diamond.gif) top left repeat;}
```

Поддерживают: Firefox 3.6+, Chrome 2+, Safari 3.1+, Opera 10.5+, IE9+  
  
**Несколько колонок:**

```
#columns {    -webkit-column-count: 2;    -webkit-column-width: 250px;    -webkit-column-gap: 35px;    -webkit-column-rule: 1px solid #6d94b4;    -moz-column-count: 2;    -moz-column-width: 240px;    -moz-column-gap: 35px;    -o-column-rule: 1px solid #6d94b4;    -o-column-count: 2;    -o-column-width: 240px;    -o-column-gap: 35px;    -o-column-rule: 1px solid #6d94b4;    column-count: 2;    column-width: 240px;    column-gap: 35px;    column-rule: 1px solid #6d94b4;}
```

Поддерживают: Firefox 3+, Chrome 2+, Safari 3.1+, Opera 11.1+, IE10+  
  
**CSS3 Box Sizing (браузер вычисляет ширину элемента)**:

```
#box-sizing {    padding: 0 30px 0 30px;    -webkit-box-sizing: border-box;    -moz-box-sizing: border-box;    -o-box-sizing: border-box;    box-sizing: border-box;}
```

Поддерживают: IE8+, Firefox 3+, Opera 9.6+, Chrome 2+, Safari 3.1+
