---
title: "Колонки одинаковой высоты"
date: ""
categories: 
  - "js"
---

![Колонки одинаковой высоты](images/1410700808_equal-height-jquery.png "Колонки одинаковой высоты")

  

```
$('.box-contain').each(function () {    var box = $(this),        boxes = $(this).find('.box'),        boxPaddingTop = $(boxes).css('padding-top'),        boxPaddingBot = $(boxes).css('padding-bottom'),        boxMarginTop = $(boxes).css('margin-top'),        boxMarginBot = $(boxes).css('margin-bottom'),        boxHeight = $(box).height(),        boxSum = parseFloat(boxHeight) - parseFloat(boxPaddingTop) - parseFloat(boxPaddingBot) - parseFloat(boxMarginTop) - parseFloat(boxMarginBot);    $(boxes).css("height", boxSum);});
```

  
[Смотреть результат](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9sZXNzb244L21nSEN0L3Nob3cv)
