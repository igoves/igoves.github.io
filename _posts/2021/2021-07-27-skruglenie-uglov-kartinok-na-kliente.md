---
title: "Скругление углов картинок на клиенте"
categories: 
  - "css"
---

![Скругление углов картинок на клиенте](images/1294340996_10.jpg "Скругление углов картинок на клиенте")

  
**HTML**  

```
<div class="b-img-radius" style="background: url(i/tmp/1.jpg); width: 250px; height: 167px"></div>
```

  
**CSS**  

```
.b-img-radius {  zoom: 1;  position: relative;  -webkit-border-radius: 10px;  -moz-border-radius: 10px;  border-radius: 10px;  display: inline-block;  vertical-align: top;}  .b-img-radius img {    display: block;    visibility: hidden;  }
```

  
Для ИЕ6-8 подключаем в css [css3pie](https://dev.xfor.top/go/aHR0cDovL2NzczNwaWUuY29tLw%3D%3D)  

```
behavior: url(css/PIE.htc);
```

  
[Демо](https://dev.xfor.top/go/aHR0cDovLzVsdmwucnUvaGgv)  
  
НУ или все же воспользоваться явой к примеру  
**CurvyCorners** о котором я когда-то писал [http://www.curvycorners.net/](https://dev.xfor.top/go/aHR0cDovL3d3dy5jdXJ2eWNvcm5lcnMubmV0Lw%3D%3D).
