---
title: "jQuery сниппеты: увеличение поля ввода при получении фокуса"
categories: 
  - "js"
---

Допустим, у нас на странице есть элемент textarea:  

```
<form>    <textarea></textarea></form>
```

  
  
Изначально этот элемент имеет размеры 250px x 125px  

```
textarea {    width: 250px;    height: 125px;}
```

  
  
Чтобы заставить это поле ввода при получении фокуса изменить свою ширину, используем простенький сниппет:  

```
$(function() {    $("textarea").focus(function(){        $(this).animate({ width:"500px"}, 1000);    }).blur(function(){        $(this).animate({ width:"250px"}, 500);    });});
```

  
  
Ну и примерчик для input [http://codepen.io/mihdan/pen/DFema](https://dev.xfor.top/go/aHR0cDovL2NvZGVwZW4uaW8vbWloZGFuL3Blbi9ERmVtYQ%3D%3D)
