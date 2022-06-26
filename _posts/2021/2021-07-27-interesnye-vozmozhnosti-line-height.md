---
title: "Интересные возможности line-height"
categories: 
  - "css"
---

Оформление каждой строки текста своим цветом  

![Интересные возможности line-height](images/1428417518_start.png "Интересные возможности line-height")

  

```
.text {  -webkit-background-clip: text;  -webkit-text-fill-color: transparent;  background-image: linear-gradient(    to bottom,    rgba(white, 0.8),    rgba(white, 0.8) $lh,    rgba(white, 0.6) $lh,    rgba(white, 0.6) $lh*2,    rgba(white, 0.4) $lh*2,    rgba(white, 0.4) $lh*3,    rgba(white, 0.2) $lh*3,    rgba(white, 0.2));}
```

  
  
Линии между строками текста

```
.parent {  padding: $lh*2;  background: #082838;  background-image: repeating-linear-gradient(    to bottom,    rgba(white, 0)   0,    rgba(white, 0)   $lh/1em*16px-1,    rgba(white, 0.1) $lh/1em*16px-1,    rgba(white, 0.1) $lh/1em*16px  );}
```

  
  
Размещение изображений на каждой строке

```
.text  background-image: url(image.svg);  background-size: $lh $lh;  background-repeat: repeat-y;  padding-left: $lh*2;}
```

  
  
Использовать сие на свой страх и риск, т.к. может чем-то не поддерживаться =)  
[ДЕМО](https://dev.xfor.top/go/aHR0cDovL2NvZGVwZW4uaW8vY2hyaXNjb3lpZXIvcGVuL1lQWkxHag%3D%3D)
