---
title: "Люблю я IE6 и еще 2 процента пользователей"
date: "2009-11-26"
categories: 
  - "css"
tags: 
  - "ie6"
  - "gemor"
---

Речь пойдет сново о багах и кул хаков для IE6.

**overflow:auto и position:relative** _html:_

```
<div id="element"><div id="anotherelement"></div></div>
```

_css:_

```
#element{
        background: #95CFEF;
        border: solid 1px #36F;
        width: 300px;
        height: 150px;  
        margin: 30px 0;
        overflow: auto;
}
#anotherelement{
        background: #555;
        width: 150px;
        height: 175px;  
        position: relative;
        margin: 30px;
}
```

Вид в нормальных браузерах:

![Люблю я IE6 и еще 2 процента пользователей](images/1258881182_12.gif "Люблю я IE6 и еще 2 процента пользователей")

Решение проблемы кроется в следующем коде:

```
#element{
        background: #C2DFEF;
        border: solid 1px #36F;
        width: 365px;   
        margin: 30px;
        padding: 5px;
        overflow: hidden;
}
```
