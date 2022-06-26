---
title: "Выделяем текущий пункт меню отдельным стилем явой jQuery"
categories: 
  - "js"
tags: 
  - "menyu"
  - "tekushchiy-punkt"
  - "hak"
  - "yava"
---

![Выделяем текущий пункт меню отдельным стилем явой jQuery](images/1325873447_11111.jpg "Выделяем текущий пункт меню отдельным стилем явой jQuery")

  
Допустим нужно выделить текущий пункт меню отдельным стилем как например сейчас выделен \\"домой\\" если это главная страница [сайта](https://dev.xfor.top) или \\"блог\\" если вы находитесь в разделе блог. Но иногда это сделать просто невозможно (в случае аякса) или сложно из за структуры меню. И тут нам на помощь приходит ява:  
  
Этот сниппет очень прост и заключается в том, что бы из полученного массива ссылок выбрать только ту, у которой атрибут href совпадает с адресом страницы.  

```
$(function () {                                      // Когда страница загрузится    $('.lmenu a').each(function () {             // получаем все нужные нам ссылки        var location = window.location.href; // получаем адрес страницы        var link = this.href;                // получаем адрес ссылки        if(location == link) {               // при совпадении адреса ссылки и адреса окна            $(this).addClass('active');  //добавляем класс        }    });});
```

  
Нужно выделить и родителей ?  
Если у вас древовидное меню, бывает, нужно выделить не только текущую ссылку но и ссылки родительских разделов, для этого используем метод Match(). Код будет таким:  

```
$(function () {                             // когда страница загружена    $('.lmenu a').each(function () {    // проходим по нужным нам ссылками        var location = window.location.href // переменная с адресом страницы        var link = this.href                // переменная с url ссылки        var result = location.match(link);  // результат возвращает объект если совпадение найдено и null при обратном        if(result != null) {                // если НЕ равно null            $(this).addClass('current');    // добавляем класс        }    });});
```

  
**UPD** Еще один способ  

```
(function($){ 	$(document).ready(function(){		var pathname = window.location.pathname,			page = pathname.split(/[/ ]+/).pop(),			menuItems = $('#main_menu a');		menuItems.each(function(){			var mi = $(this),				miHrefs = mi.attr("href"),				miParents = mi.parents('li');			if(page == miHrefs) {				miParents.addClass("active").siblings().removeClass('active');			}		});	});})(jQuery);
```
