---
title: "CSS сниппеты"
date: ""
categories: 
  - "css"
---

**Размытый текст**  

```
.blur{  color: transparent;  text-shadow: 0 0 3px rgba( 0, 0, 0, 0.5);  }
```

  
  
**Предварительная загрузка изображения**  

```
body:before {    content: url(images/hover3.gif);    display:none;}
```

  
  
**Текст с градиентом**  

```
h1 {  font-size: 20px;  background: -webkit-linear-gradient(#eee, #333);  -webkit-background-clip: text;  -webkit-text-fill-color: transparent;}
```

  
  
Прозрачность изображений  

```
img {opacity:0.4;filter:alpha(opacity=40); /* For IE8 and earlier */}
```

  
  
**Несколько фонов**  

```
#Multiple-Backgrounds {width: 500px;height: 250px;background: url(decoration.png) left top no-repeat, url(ribbon.png) right bottom no-repeat, url(old_paper.jpg) left top no-repeat;}
```
