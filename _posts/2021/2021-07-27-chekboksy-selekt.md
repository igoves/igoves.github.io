---
title: "Чекбоксы вместо селект"
date: ""
categories: 
  - "js"
tags: 
  - "vvshop"
---

![Чекбоксы вместо селект](images/1375962469_untitled-1.jpg "Чекбоксы вместо селект")

  
Есть четыре флажка - Пометить можно только один, а так же его снять при необходимости.  
Получается замена стандартного селекта(2 клика) на чекбокс (1 клик)  

```
<script>$(function() {					$('.test').click(function () {		$('.test').parent().addClass('muted');		if (this.checked) {			$('.test').attr('checked',false);			$(this).parent().toggleClass('muted');			this.checked=true;		};	});			});</script>			<label class="checkbox inline muted" style="margin-right:10px">	<input type="checkbox" value="1" class="test" name="flag" />СУПЕРЦЕНА</label><label class="checkbox inline muted" style="margin-right:10px">	<input type="checkbox" value="2" class="test" name="flag" />АКЦИЯ</label><label class="checkbox inline muted" style="margin-right:10px">	<input type="checkbox" value="3" class="test" name="flag" />ТОП ПРОДАЖ</label><label class="checkbox inline muted">	<input type="checkbox" value="4" class="test" name="flag" />НОВИНКА</label>	
```

  
Такая штука была реализована в админке [vvShop](https://dev.xfor.top/go/aHR0cDovL3Zlc2Vsb3Yuc3VteS51YS92dnNob3Av)
