---
title: "CSS zoom эффект при наведении на картинку"
categories: 
  - "css"
---

![CSS zoom эффект при наведении на картинку](images/1403945083_untitled-1.png "CSS zoom эффект при наведении на картинку")

  

```
* {    -webkit-transition: -webkit-transform 0.3s linear;    -moz-transition: -moz-transform 0.3s linear;    -o-transition: -o-transform 0.3s linear;    transition: transform 0.3s linear;}img {    float: left;    padding:10px;}img:hover {    -webkit-transform: scale(1.08);    -moz-transform: scale(1.08);    -ms-transform: scale(1.08);    -o-transform: scale(1.08);    transform: scale(1.08);}
```

  
[ДЕМО](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9sZXNzb244LzZmc0dTL3Nob3cv)
