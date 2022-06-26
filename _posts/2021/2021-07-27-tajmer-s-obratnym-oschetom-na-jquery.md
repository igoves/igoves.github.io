---
title: "Таймер с обратным отсчетом на jQuery"
categories: 
  - "js"
tags: 
  - "vremya"
  - "otschet-nazad"
  - "taymer"
---

![Таймер с обратным отсчетом на jQuery](images/1292064799_untitled-1.jpg "Таймер с обратным отсчетом на jQuery")

  

```
<script type="text/javascript">var timetogo = 20;var timer = window.setInterval(function(){    var str = timetogo;    $('#counter').text(str);        if (timetogo <= 0)    {          $('#newdiv').text('Время вышло');         window.clearInterval(timer);    }    timetogo--;}, 1000);</script> 
```

  

```
<div id="counter">здесь отсчет</div><div id="newdiv">А здесь появится текст о том что время вышло</div>
```

  
Данный пример, отсчитывает в контейнере counter 20 секунд после чего появится текст \\"Время вышло\\". Видел в просторах интернета скрипт **Timer Jquery**, но он считает вперед. Этот код отсчитывает назад.
