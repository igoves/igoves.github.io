---
title: "Колонки одинаковой высоты"
date: "2009-09-03"
categories: 
  - "note"
tags: 
  - "vysota"
  - "kolonki"
---

**Хинт**: для того что бы у Вас работало несколько версий IE юзайте tredosoft.com/Multiple\_IE

Особенностью табличной верстки является то, что колонки, получаемые с помощью ячеек таблицы, имеют одну высоту. Это неудивительно, поскольку ячейки взаимосвязаны и при повышении высоты одной ячейки, соответственно увеличивается высота рядом расположенных ячеек. Многие разработчики пытаются произвести подобный эффект и с помощью слоев, т.е. сделать их взаимосвязанными и одной высоты, независимо от объема содержимого. Но это **НЕПРАВИЛЬНО**!

А правильно Вот так:

```
<style type="text/css">
#container {
 border-left: 200px solid maroon; /* Цвет и ширина левой колонки */
 background: #f0f0f0; /* Цвет фона правой колонки */
} 

#col1 {
 width: 200px; /* Ширина левой колонки */
 float: left; /* Превращаем в плавающий элемент */
 margin-left: -200px; /* Сдвигаем все влево на ширину границы */
 color: #fff; /* Цвет текста в колонке */
}

#col1 p {
 padding: 5px; /* Поля вокруг абзаца текста */ 
 margin: 0; /* Обнуляем отступы */ 
}

#col2 {
 padding: 5px;
}

div.clear {
 clear: both; /* Убираем все плавающие элементы */
}
</style>
</head>
<body>
<div id="container">
<div id="col1">
<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diem nonummy nibh euismod tincidunt ut lacreet dolore magna aliguam erat volutpat.</p>
</div>
<div id="col2">
Ut wisi enim ad minim veniam, quis nostrud exerci taion ullamcorper suscipit lobortis nisl ut aliquip ex en commodo consequat. Duis te feugifacilisi per suscipit lobortis nisl ut aliquip ex en commodo consequat.Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diem nonummy nibh euismod tincidunt ut lacreet dolore magna aliguam erat volutpat.
</div>
<div class="clear">&nbsp;</div>
</div>
```
