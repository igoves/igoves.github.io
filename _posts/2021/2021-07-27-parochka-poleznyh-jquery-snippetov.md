---
title: "Парочка полезных jQuery сниппетов"
categories: 
  - "js"
---

Загрузка внешнего контента

```
$("#content").load("somefile.html", function(response, status, xhr) {  // error handling  if(status == "error") {    $("#content").html("An error occured: " + xhr.status + " " + xhr.statusText);  }});
```

  
Частичное обновление страницы

```
setInterval(function() {  $("#refresh").load(location.href+" #refresh>*","");}, 10000); // milliseconds to wait
```

load по ссылке подгрузит всю страницу, а с #refresh возьмет из всей страницы только элемент #refresh (а >\* все что в нем), и вставит его в существующий #refresh  
  
Предзагрузка изображений

```
$.preloadImages = function() {       for(var i = 0; i<arguments.length; i++) {               $("<img />").attr("src", arguments[i]);       }}$(document).ready(function() {       $.preloadImages("hoverimage1.jpg","hoverimage2.jpg");});
```
