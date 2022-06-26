---
title: "Очистить форму на jQuery"
categories: 
  - "js"
---

```
$(':input','#myform')  .not(':button, :submit, :reset, :hidden')  .val('')  .removeAttr('checked')  .removeAttr('selected');
```
