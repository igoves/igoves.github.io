---
title: "Полный ресайз бекграунда с плавной заменой изображения"
date: ""
categories: 
  - "css"
tags: 
  - "jquery"
  - "js"
  - "opacity"
  - "slider"
  - "zatuhanie"
  - "rotator"
  - "slayder"
---

Помните пост [Полный ресайз бекграунда не зависимо от размеров окна браузера](https://dev.xfor.top/513-polnyj-resajz-bekgraunda-ne-zavisimo-ot-razmerov-okna-brauzera.html)  

![Полный ресайз бекграунда с плавной заменой изображения](images/1290861802_untitled-1.jpg "Полный ресайз бекграунда с плавной заменой изображения")

  
Сегодня сделаем так что бы бекграунд еще и с эффектом затухания слайдилась  
  

```
function backgroundScale(){    var imageRatio       = 1.75;    var windowHeight     = document.body.clientHeight;    var windowWidth      = document.body.clientWidth;    var windowScale      = windowWidth / windowHeight;    var targetWidth      = windowHeight * imageRatio;    var targetWidthFull  = windowWidth;    var leftPos          = - (targetWidth - windowWidth) / 2;    var leftPosFull      = 0;    if (windowScale <= imageRatio)    {        $('#rotator img').attr("width", targetWidth);        $('#rotator').css("left", leftPos);    }     else    {        $('#rotator img').attr("width", targetWidthFull);        $('#rotator').css("left", leftPosFull);    }}$(window).resize(function(){    var imageRatio       = 1.75;    var windowHeight     = document.body.clientHeight;    var windowWidth      = document.body.clientWidth;    var windowScale      = windowWidth / windowHeight;    var targetWidth      = windowHeight * imageRatio;    var targetWidthFull  = windowWidth;    var leftPos          = - (targetWidth - windowWidth) / 2;    var leftPosFull      = 0;    if (windowScale <= imageRatio)    {        $('#rotator img').attr("width", targetWidth);        $('#rotator').css("left", leftPos);    }     else     {        $('#rotator img').attr("width", targetWidthFull);        $('#rotator').css("left", leftPosFull);    }    mainBaseResize();});$(document).ready(function(){    //$('body').css({background: #fff});    backgroundScale();     theRotator();});
```

  
  
**А теперь в скрипт добавляем эти функции**  

```
function theRotator() {    $('#rotator img').css({opacity: 0.0});    $('#rotator img:first').css({opacity: 1.0});    setInterval('rotate()',7000);} function rotate() {        // Берем первую картинку    var current = ($('#rotator img.show')?  $('#rotator img.show') : $('#rotator img:first'));     // Берем следующую картинку, когда дойдем до последней начинаем с начала    var next = ((current.next().length) ? ((current.next().hasClass('show')) ? $('#rotator img:first') :current.next()) : $('#rotator img:first'));        // Рандом    var sibs = current.siblings();    var rndNum = Math.floor(Math.random() * sibs.length );    var next = $( sibs[ rndNum ] );     // Подключаем эффект растворения/затухания для показа картинок, css-класс show имеет больший z-index    next.css({opacity: 0.0})    .addClass('show')    .animate({opacity: 1.0}, 1000);     // Прячем текущую картинку    current.animate({opacity: 0.0}, 1000)    .removeClass('show');};
```

  
[СМОТРЕТЬ РЕЗУЛЬТАТ](https://dev.xfor.top/uploads/files/demo/036/index.html) (Каждые 7 секунд смена бекграунда)
