---
title: "Вывод динамической даты и времени на jQuery + momentjs"
categories: 
  - "js"
---

![Вывод динамической даты и времени на jQuery + momentjs](images/1418158145_1.png "Вывод динамической даты и времени на jQuery + momentjs")

  

```
<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script><script src="http://cdn.jsdelivr.net/momentjs/2.8.4/moment.min.js"></script><script>    function update() {      $("#today_date").text(moment().format('DD.MM.YYYY H:mm:ss'));      var now = moment(),          second = now.seconds() * 6,          minute = now.minutes() * 6 + second / 60,          hour = ((now.hours() % 12) / 12) * 360 + 90 + minute / 12;    }    function timedUpdate() {      update();      setTimeout(timedUpdate, 1000);    }    timedUpdate();</script><h1 id="today_date"></h1>
```
