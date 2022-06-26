---
title: "Пролистывание страницы вниз (scroll to bottom) на jQuery"
date: ""
categories: 
  - "js"
tags: 
  - "bottom"
  - "jquery"
  - "scroll"
---

Т.к. функции scrollBottom не существует, то делается вот такой хук:  

```
$("a[href='#bottom']").click(function() {
  $("html, body").animate({ scrollTop: $(document).height() }, "slow");
  return false;
});
```

По клику на #bottom пролистывается страница вверх на высоту документа и таким образом получаем прокрутку в низ страницы с анимацией =)
