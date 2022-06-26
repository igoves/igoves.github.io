---
title: "Напоминалка о селекторах в CSS"
categories: 
  - "note"
tags: 
  - "css"
  - "brauzery"
  - "selektor"
---

pseudoElement  

```
p::first-line {     font-weight: bold;     font-size: 1.2em;  }  
```

  
Первая линия абзаца  

```
p::first-letter {     float: left;     font-size: 2em;     font-weight: bold;     font-family: cursive;     padding-right: 2px;  }  
```

  
Первая буква абзаца  
Поддерживает этот селектор IE6+ Firefox Chrome Safari Opera  
  
  
**X:nth-child(n)**  

```
li:nth-child(3) {     color: red;  } 
```

  
Красным третий li  
Поддерживает этот селектор IE9+ Firefox 3.5+ Chrome Safari  
  
**X:nth-last-child(n)** - тоже самое что и предыдущий только отсчет с конца  
  
Их конечно больше. Но и эти как по мне редко используются. А сейчас **бонус**:  

```
a {  -moz-transform: scale(1.1);  -webkit-transform: scale(1.1);  -o-transform: scale(1.1);}
```

  
При наведении на ссылку сделает ее на 10% больше  
  

```
div {  background-color: #999; /* all browsers */  *background-color: #ccc; /* add a * before the property - IE7 and below */  _background-color: #000; /* add a _ before the property - IE6 and below */}
```

  
Верстаем под разные версии ИЕ -)  
  

```
div {/* standards-compliant browsers */opacity:0.7;/* The following is ignored by standards-based browsers */-ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=70)";  /* IE8 */filter: alpha(opacity=70); /* IE 5-7  */}
```

  
Выставляем прозрачность с учетом версий ИЕ  
  

```
a { white-space: nowrap; }
```

  
Не рвать ссылку на строки
