---
title: "Ошибки IE6 или опять о кроссбраузерности"
date: "2009-11-22"
categories: 
  - "css"
tags: 
  - "ie"
  - "ie"
  - "hak"
---

Что это \\"великий\\" и \\"могучий\\" бразуер я писать опять не буду, просто приведу некоторые ошибки ИЕ и варианты фикса:

В основном все используют для создания навигационного меню списки. А если нужно сделать меню горизонтальным, просто ставят float:left на ссылки внутри списка. Смотрим код:

_html_

```
<ul>
    <li><a href="#"></a></li>
    <li><a href="#"></a></li>
    <li><a href="#"></a></li>
</ul>
```

_css_

```
ul {
    list-style: none;
}

ul li a {
        display: block;
        width: 130px;
        height: 30px;
        text-align: center;
        color: #fff;
        float: left;
        background: #95CFEF;
        border: solid 1px #36F;
        margin: 30px 5px;
}
```

Вот, что мы увидим в нормальных браузерах:

![Ошибки IE6 или опять о кроссбраузерности](images/1258880580_6.gif "Ошибки IE6 или опять о кроссбраузерности")

Решение 1: _css_

```
li a {
        background: #95CFEF;
        display: block;
        width: 200px;
}
```

Решение 2: _css:_

```
li a {
        background: #95CFEF;
        float: left;
        clear: left;
}
```
