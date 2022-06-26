---
title: "CSS оборвать строку троеточием"
categories: 
  - "css"
---

![CSS оборвать строку троеточием](images/1403944945_untitled-2.png "CSS оборвать строку троеточием")

  

```
.text-overflow {    white-space: nowrap;       /* Перво-наперво, запретим перенос строк */    overflow: hidden;          /* Скрываем текст, который не помещается в блок */    text-overflow: ellipsis;   /* Уводим текст в многоточие */    display: block;            /* Элемент обязательно должен быть блочным */}
```
