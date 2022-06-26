---
title: "Подсветка при наведении пересечения таблицы jQuery"
date: ""
categories: 
  - "js"
---

![Подсветка при наведении пересечения таблицы jQuery](images/1389442698_jquery-highlight-table-row-and-column-mouseover.png "Подсветка при наведении пересечения таблицы jQuery")

  

```
$('td').mouseover(function () {    $(this).siblings().css('background-color', '#EAD575');    var ind = $(this).index();    $('td:nth-child(' + (ind + 1) + ')').css('background-color', '#EAD575');});$('td').mouseleave(function () {    $(this).siblings().css('background-color', '');    var ind = $(this).index();    $('td:nth-child(' + (ind + 1) + ')').css('background-color', '');});
```
