---
title: "Добавление полей в форму динамически jQuery"
categories: 
  - "js"
---

![Добавление полей в форму динамически jQuery](images/1397302599_untitled-2.jpg "Добавление полей в форму динамически jQuery")

  

```
<html><head><title>Добавление полей динамически</title><style type="text/css">fieldset {	width: 450px;}ul {	padding: 2px;	list-style: none;}label {	float: left;	width: 100px;}</style><script type="text/javascript" src="jquery.js"></script><script type="text/javascript">$(document).ready(function () {	$('#add').click(function(){		var str = '<li>';		str+= '<label>ФИО</label><input type="text" value=""/> ';		str+= '<input type="button" value="Удалить" class="remove"/>';		str+= '</li>';		$('#sites').append(str);	});	$('.remove').live('click', function() {		$(this).parent('li').remove();	});});</script></head><body><form action="send.php" method="post">  <fieldset>    <legend>Форма</legend>    <ul id="sites">      <li>        <label>ФИО</label>        <input type="text" name="fio[]" />      </li>    </ul>    <input type="button" id="add" value="Добавить еще"/>  </fieldset></form></body></html>
```
