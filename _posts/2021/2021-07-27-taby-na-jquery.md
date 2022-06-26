---
title: "Табы на Jquery"
categories: 
  - "js"
tags: 
  - "jquery"
  - "tabs"
  - "taby"
---

![Табы на Jquery](images/1307038235_tabs.png "Табы на Jquery")

  
Самый просто из виденных мною способов построения Табов:  

```
(function($) {$(function() {    $('ul.tabs').delegate('li:not(.current)', 'click', function() {        $(this).addClass('current').siblings().removeClass('current')            .parents('div.section').find('div.box').hide().eq($(this).index()).fadeIn(150);    })})})(jQuery)
```

  
[СМОТРЕТЬ](https://dev.xfor.top/uploads/files/demo/039/index.html) / [Скачать](https://dev.xfor.top/go/aHR0cDovL2RpbW94Lm5hbWUvZG93bmxvYWQtbWFuYWdlci5waHA%2FaWQ9NDk%3D)
