---
title: "Верстаем вот такой блочек на CSS"
date: ""
categories: 
  - "css"
tags: 
  - "css"
  - "marker"
  - "blok"
---

![Верстаем вот такой блочек на CSS](images/1349702423_untitled-1.jpg "Верстаем вот такой блочек на CSS")

  

```
<div style="width:200px; height:200px; border:1px solid #ccc; display:block" class="ribbon">asdf<p><span>Новое</span></p></div><style>.ribbon {    color: #fff;    position: relative;    display: inline-block;    overflow: hidden;    padding: 5px;    font-weight: 900;    font-family: Arial, sans-serif;}.ribbon p span {    -moz-transform: rotate(45deg);    -ms-transform: rotate(45deg);    -webkit-transform: rotate(45deg);    -o-transform: rotate(45deg);    display: inline-block;    right: -26px;    text-align: center;    position: absolute;    text-transform: uppercase;    box-shadow: 0px 0px 10px rgba(0,0,0,0.2), inset 0px 5px 30px rgba(255,255,255,0.2);    top: 21px;    background: red;    width: 100px;    padding: 3px 10px;}	</style>
```
