---
title: "Разъезжающийся textarea по фокусу на jQuery"
categories: 
  - "js"
tags: 
  - "jquery"
  - "textarea"
---

Этот скрипт используется [здесь на сайте](https://dev.xfor.top) в поле ввода комментариев  

```
var element = $('textarea[name=comments]');
var orig_height = 56;	// высота оригинала
var new_height = 160; 	// высота когда разьехался

element.focus(function (){
	$(this).animate({height: new_height + 'px'});	// развернуть
});
element.blur(function (){
	if (!element.val().length ) {
		$(this).animate({height: orig_height + 'px'});	// свернуть если нет текста
	} 
});
```

[http://jsfiddle.net/MgcDU/10438/](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9NZ2NEVS8xMDQzOC8%3D)
