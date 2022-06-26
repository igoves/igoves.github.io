---
title: "Полезные сниппеты на jQuery"
categories: 
  - "js"
---

![Полезные сниппеты на jQuery](images/1322643912_68.jpg "Полезные сниппеты на jQuery")

  
  
**Предзагрузка изображений**  

```
(function($) {  var cache = [];  // Arguments are image paths relative to the current page.  $.preLoadImages = function() {    var args_len = arguments.length;    for (var i = args_len; i--;) {      var cacheImage = document.createElement('img');      cacheImage.src = arguments[i];      cache.push(cacheImage);    }  }jQuery.preLoadImages("image1.gif", "/path/to/image2.png");
```

  
Пока изображение не загрузилось будет светиться image1.gif  
  
  
**Замена target=”blank”**  

```
$('a[@rel$='external']').click(function(){     this.target = "_blank";});
```

  
Как-то так

```
<a href="http://veselov.sumy.ua" rel="external">veselov.sumy.ua</a>
```

и откроется в новом окне  
  
  
**Плавный скролл до якоря**  

```
$(document).ready(function() {    $("a.topLink").click(function() {        $("html, body").animate({            scrollTop: $($(this).attr("href")).offset().top + "px"        }, {            duration: 500,            easing: "swing"        });        return false;    });});
```

  
  
  
**Плавное затухание ссылки при наведении**  

```
$(document).ready(function(){    $(".thumbs img").fadeTo("slow", 0.6); // This sets the opacity of the thumbs to fade down to 60% when the page loads    $(".thumbs img").hover(function(){        $(this).fadeTo("slow", 1.0); // This should set the opacity to 100% on hover    },function(){        $(this).fadeTo("slow", 0.6); // This should set the opacity back to 60% on mouseout    });});
```

  
  
  
**Колонки одинаковой высоты**  

```
var max_height = 0;$("div.col").each(function(){    if ($(this).height() > max_height) { max_height = $(this).height(); }});$("div.col").height(max_height);
```

  
  
  
**Получить параметры урла**  

```
$.urlParam = function(name){    var results = new RegExp('[\\\\?&]' + name + '=([^&#]*)').exec(window.location.href);    if (!results) { return 0; }    return results[1] || 0;}
```
