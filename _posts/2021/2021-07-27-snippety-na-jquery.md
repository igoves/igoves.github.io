---
title: "Сниппеты на jquery"
categories: 
  - "js"
tags: 
  - "jquery"
  - "snippety"
---

![Сниппеты на jquery](images/1330722509_20.jpg "Сниппеты на jquery")

  
**Как узнать, имеется ли на странице элемент**  

```
if ( $('#myDiv').length ) { /* что-то делаем */}
```

  
  
**Как запретить/разрешить элемент (disable/enable)**  

```
$("#x").attr("disabled","disabled");$("#x").removeAttr("disabled");
```

  
  
**Как сделать выбор/отмену выбора чекбокса (check/uncheck)**  

```
$("#x").attr("checked", "checked");$("#x").attr("checked","");
```

  
  
**Как получить значение выбранного элемента в селекте**  

```
<select id="sel"><option value="1">vremenno</option><option value="2">net</option></select>$("select#sel").val();$("#sel option:selected").text();
```

  
  
**Как выбрать элементы, у которых в ID есть спецсимволы (\\".\\", \\"\[\\", и т.п.)**  

```
$("#some.id") // не работает$("#some\\.id") // работает
```

  
  
**Как определить, прописан ли у элемента класс (эта функция появилась в jQuery 1.2)**  

```
$('#something').hasClass("someClass")
```

  
  
**Плавное изменение цвета**  

```
$(document).ready( function() {$(".mainMenu a, .articleTitle a").mouseover( function() {$(this).animate({color: "#cc4e4e"}, {queue:false, duration:250 });}).mouseout( function() {$(this).animate({color: "#0e8db7"}, { queue:false, duration:350});});});
```

  
  
**Выбрать все чекбоксы конкретного объекта**  

```
function checkall(context){$("#"+context).find("input[@type$='checkbox']").each(function(){this.checked = checked;});}
```

  
  
**Количество выбранных элементов**  

```
$('element').size();
```

  
  
**Состояние радиобаттона**  

```
var var_name = $("input[@name='radio_name']:checked").val();
```

  
  
**Перехват изменения размера окна**  

```
function doSomething() {alert("Я закончил изменение размера!");};var resizeTimer = null;$(window).bind('resize', function() {if (resizeTimer) clearTimeout(resizeTimer);resizeTimer = setTimeout(doSomething, 100);});
```

  
  
**Расположение объекта по центру экрана**  

```
jQuery.fn.center = function()     {    var w = $(window);    this.css("position","absolute");    this.css("top",(w.height()-this.height())/2+w.scrollTop() + "px");    this.css("left",(w.width()-this.width())/2+w.scrollLeft() + "px");    return this;    }
```

  
  
**Замена текста внутри элемента, используя регулярные выражения**  
Полезно, например при замене «скрыть» - «показать»  

```
jQuery.fn.toggleText = function(a,b)     {    return this.html(this.html().replace(new RegExp("("+a+"|"+b+")"),    function(x){return(x==a)?b:a;}));    }
```

  
  
**Запуск события resize после задержки**  
Задержка нужна по той причине, что событие resize() постоянно, пока юзер изменяет размер окна. А с использование этой функции, ресайз будет запускаться только через некоторое количество мс после того, как юзер прекратит изменять размер экрана.  

```
jQuery.fn.resizeComplete = function(fn, ms)     {    var timer = null;    this.resize(function()         {        if (timer)             {            clearTimeout(timer);            }        timer = setTimeout(fn,ms);        });    }
```
