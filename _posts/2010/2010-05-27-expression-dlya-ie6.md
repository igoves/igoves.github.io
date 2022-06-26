---
title: "Expression для IE6"
date: "2010-05-27"
categories: 
  - "css"
tags: 
  - "expression"
  - "ie-sux"
  - "ie6"
  - "verstka"
---

**Эмуляция position:fixed**

```
html{
   background: url('/0.gif') no-repeat; 
   background-attachment: fixed; /*избавляемся от дергания при вертикально прокрутки*/
   }  
#header{
    width: 100%;
    padding: 0.5em 0;
    background-color: #000; 
    color: #fff;
    position: fixed;
    top: 0;
    left: 0;
    //position: absolute;
    //top: expression(eval(document.documentElement.scrollTop) + 'px');
   }

#content{
   height:4000px;
   }
```

```
<div id="header">Эмуляция fixed</div>
<div id="content">Какой-то контент</div>
```

**Вертикальное выравнивание в CSS**

```
#out{
   height:500px;
   display:table-cell;
   vertical-align:middle;
}
         
#centered {
   margin-top: expression(((outer.offsetHeight/2)-parseInt(offsetHeight)/2)&lt;0 ? "0" : (centered.offsetHeight/2)-(parseInt(offsetHeight)/2) +'px');
}
```

```
<div id="out">
   <p id="centered">...</p>
</div>
```

**Избавляемся от моргания фонового изображения в IE**

```
   body{
      filter: expression(document.execCommand("BackgroundImageCache", false, true));
   }
```

**min-width и max-width в IE6**

```
   #container 
   { 
       min-width: 600px; 
       max-width: 1200px; 
       width:expression(document.body.clientWidth < 600? "600px" : document.body.clientWidth > 1200? "1200px" : "auto"); 
   }
```

**PNG для IE6 (не проверял)**

```
* html img, * html .png{
position:relative;
behavior: expression((this.runtimeStyle.behavior="none")&&(this.pngSet?this.pngSet=true:(this.nodeName == "IMG" && this.src.toLowerCase().indexOf('.png')>-1?(this.runtimeStyle.backgroundImage = "none",
this.runtimeStyle.filter = "progid:DXImageTransform.Microsoft.AlphaImageLoader(src='" + this.src + "', sizingMethod='image')",
this.src = "transparent.gif"):(this.origBg = this.origBg? this.origBg :this.currentStyle.backgroundImage.toString().replace('url("','').replace('")',''),
this.runtimeStyle.filter = "progid:DXImageTransform.Microsoft.AlphaImageLoader(src='" + this.origBg + "', sizingMethod='crop')",
this.runtimeStyle.backgroundImage = "none")),this.pngSet=true)
);
}
```

С expression забудьте о валидации и о хорошей производительности.
