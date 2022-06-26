---
title: "Интересные штуки с CSS"
categories: 
  - "css"
tags: 
  - "css"
  - "hook"
  - "webkit"
---

![Интересные штуки с CSS](images/1333789926_7.jpg "Интересные штуки с CSS")

  
Что бы талица была зеброй  

```
table tr {   background: white;}table tr:nth-child(odd) {   background: #f4f4f4;}    
```

  
А теперь что бы еще и подсвечивался рядок при наведении  

```
.table tbody tr:hover td{  background-color: #f5f5f5;}
```

  
Прячим всплывающее окно при наведении на урл  

```
a.js-only {  -webkit-touch-callout: none;}
```

  
Задавая это свойство элементу вы можете определять то, как будет выглядеть элемент SPAN. Например, как radio button:  

```
span.lookLikeRadio {  -webkit-appearance: radio;}
```

  
Оказывается, маску при вводе пароля можно изменять. Например, вместо кружков можно отображать квадраты.  

```
input[type="password"] {  -webkit-text-security: square;}
```

  
На этом все. Не забывайте [подписываться](http://feeds2.feedburner.com/glib).
