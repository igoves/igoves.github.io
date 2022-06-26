---
title: "Тень для блока кроссбраузерно с помощью CSS"
date: ""
categories: 
  - "css"
tags: 
  - "cross"
  - "css"
  - "demo"
  - "shadow"
---

Cпособ кроссбраузерной реализации css-свойства box-shadow.  
для обычных браузеров  

```
div {    background: green; /* обязательно для ie */    -webkit-box-shadow: 0px 0px 15px #222;    -moz-box-shadow: 0px 0px 15px #222;    box-shadow: 0px 0px 15px #222;}
```

  
Суть реализации свойства box-shadow для ie сводится к четырёхкратному применению фильтра shadow с разными значениями direction. Таким образом тень начинает обрамлять весь контур контейнера.  
  
для ИЕ  

```
<!--[if IE]><style type="text/css">    div {        filter:        progid:DXImageTransform.Microsoft.Shadow(color='#042b47', Direction=45, Strength=6)        progid:DXImageTransform.Microsoft.Shadow(color='#042b47', Direction=135, Strength=6)        progid:DXImageTransform.Microsoft.Shadow(color='#042b47', Direction=225, Strength=6)        progid:DXImageTransform.Microsoft.Shadow(color='#042b47', Direction=315, Strength=6);        position: relative;        top: -12px;        left: -12px;        zoom: 1;    }</style><![endif]-->
```

  
Несколько нюансов, на которые стоит обратить внимание:  

Тень, при использовании фильтра получается темнее, поэтому, чтобы добиться идентичности, нужно поиграться с параметрами color и strength  
IE увеличивает размеры блока на ширину тени, а так как для каждой стороны у нас по сути две тени, то и увеличение размеров становится двоекратным. Т.е. в конце нам нужно относительно сместить блок влево и вверх по формуле left = top = -(strength\*2)  
IE6 и IE7 требуют hasLayout, поэтому для них ставим zoom: 1 (или ширину, высоту и другие свойства, которые присваивают hasLayout)  
Для блока обязательно нужно задавать фон, иначе фильтр будет применяться к дочерним элементам

  
Минусы:

Фильтры — это всегда лишние тормоза  
IE выключает сглаживание текста внутри блока с фильтрами  
Тень в IE по форме отличается от тени в других браузерах (более квадратная)  
Внутри таким образом оформленного блока перестаёт работать alphaImageLoader (возможно и другие фильтры тоже — не проверял)

  

взято с хабра

  
[Демо](https://dev.xfor.top/go/aHR0cDovL3dpcC5hY2RzdHVkaW8ucnUvY29zbW8vYm94LXNoYWRvdy8%3D)
