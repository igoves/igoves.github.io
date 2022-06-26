---
title: "Верстка флажков для единицы продукции"
date: ""
categories: 
  - "css"
tags: 
  - "flajek-dlya-im"
  - "flajki"
---

Помните мы верстали [вот такой](https://dev.xfor.top/1018-verstaem-vot-takoy-blochek-na-css.html) блочек.  
![Верстка флажков для единицы продукции](images/1363716255_untitled-1.jpg "Верстка флажков для единицы продукции")  

  

```
<div style="width:200px; height:200px; border:1px solid #333; display:block" class="ribbon">Блочек<span>Новое</span></div><style>.ribbon {    color: #000;    position: relative;    display: inline-block;    overflow: hidden;    padding: 5px;    font-weight: 900;    font-family: Arial, sans-serif;}.ribbon span {  -webkit-transform: rotate(45deg);  -moz-transform: rotate(45deg);  -ms-transform: rotate(45deg);  -o-transform: rotate(45deg);  transform: rotate(45deg);  display: inline-block;  right: -26px;  position: absolute;  background-color: #7fcb2a;  background-image: -webkit-gradient(linear, left top, left bottom, color-stop(0%, #7fcb2a), color-stop(100% #588c1d));  background-image: -webkit-linear-gradient(top, #7fcb2a 0%, #588c1d 100%);  background-image: -moz-linear-gradient(top, #7fcb2a 0%, #588c1d 100%);  background-image: -ms-linear-gradient(top, #7fcb2a 0%, #588c1d 100%);  background-image: -o-linear-gradient(top, #7fcb2a 0%, #588c1d 100%);  background-image: linear-gradient(top, #7fcb2a 0%, #588c1d 100%);  -webkit-box-shadow: 0px 0px 3px rgba(0, 0, 0, 0.3);  -moz-box-shadow: 0px 0px 3px rgba(0, 0, 0, 0.3);  box-shadow: 0px 0px 3px rgba(0, 0, 0, 0.3);	  top: 21px;  width: 100px;  padding: 3px 10px;  text-shadow: 0px 1px 0px rgba(255, 255, 255, 0.5);  font: bold 15px Sans-Serif;  text-align: center;  color: #304d10;	}	</style>
```
