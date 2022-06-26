---
title: "Центрирование нескольких блоков DIV"
date: ""
categories: 
  - "css"
---

Часто верстальщики сталкиваются с центрированием блока фиксированной ширины. Если один элемент, то все просто **margin:0 auto**. А если несколько?  

![Центрирование нескольких блоков DIV](images/1278580822_bezimeni-1.jpg "Центрирование нескольких блоков DIV")

Один из лучших способов приведу:  

```
#parent {    border: solid 1px #aaa;    text-align: center;    white-space: nowrap;    font-size: 20px;    letter-spacing: 35px;    line-height: 12px;    overflow: hidden;    width: 615px;}.child {    width: 100px;    height: 100px;    border: solid 1px #ccc;    display: inline-block;    letter-spacing: normal;    font-size: normal;    white-space: normal;    text-align: normal;    vertical-align: middle;}.child {    *display: inline;    *margin: 0 20px 0 20px;}
```

  
Последние два параметра для ИЕ6 и ИЕ7  

```
<div id="parent">    <div class="child">    <p>This is the first box with text.</p>    </div>    <div class="child">    <p>This is another box</p>    </div>    <div class="child">    <p>This is a box</p>    </div>    <div class="child">    <p>This is a box</p>        </div></div>
```

  
И да прибудет с Вами сила -)
