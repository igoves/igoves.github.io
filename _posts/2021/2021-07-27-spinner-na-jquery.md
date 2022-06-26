---
title: "Spinner на jquery"
date: ""
categories: 
  - "js"
tags: 
  - "spinner"
---

```
<table class="gCounter"><tr><td><span id="gCounterSpan">1</span></td><td><a href="#" class="counterUp">+</a><br><a href="#" class="counterDown">-</a></td><td>&nbsp;шт.</td></tr></table>
```

  

```
        $('.counterUp').click(function() {            var tmParent = $(this).parent("td").parent('tr');            var count = tmParent.children('td').children('span').html();            count++;            tmParent.children('td').children('span').html(count);            return false;        });                $('.counterDown').click(function() {            var tmParent = $(this).parent("td").parent('tr');            var count = tmParent.children('td').children('span').html();            if (count > 1) {                count--;            }            tmParent.children('td').children('span').html(count);            return false;        });
```

  
[http://jsfiddle.net/LzNVZ/](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9Mek5WWi8%3D)
