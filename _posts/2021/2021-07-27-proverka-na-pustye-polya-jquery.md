---
title: "Проверка на пустые поля jQuery"
date: ""
categories: 
  - "js"
---

![Проверка на пустые поля jQuery](images/1397303067_untitled-4.jpg "Проверка на пустые поля jQuery")

  

```
<html><head><title>Validate empty fields</title><style type="text/css">body {	font-family: "Trebuchet MS", verdana;	width: 450px;}.error {	color: red;}#info {	color: #008000;	font-weight: bold;}</style><script type="text/javascript" src="jquery.js"></script><script type="text/javascript">    $(document).ready(function () {        $('#check').click(validate);        function validate() {            var dataValid = true;            $('#info').html('');            $('.required').each(function () {                var cur = $(this);                cur.next('span').remove();                if ($.trim(cur.val()) == '') {                    cur.after('<span class="error"> Что-то не заполнено</span>');                    dataValid = false;                }            });            if (dataValid) {                $('#info').html('Все впордке можно отправлять');            }        }    });</script></head><body><form>  <fieldset>    <table>      <tbody>        <tr>          <td>ФИО:* </td>          <td><input type="text" class="required" /></td>        </tr>        <tr>          <td>Адресс:* </td>          <td><input type="text" class="required"/></td>        </tr>        <tr>          <td>Город: </td>          <td><input type="text"/></td>        </tr>        <tr>          <td>Страна:* </td>          <td><input type="text" class="required"/></td>        </tr>      </tbody>    </table>  </fieldset>  <br/>  <span id="info"></span> <br/>  <input type="button" value="Проверить" id="check" /></form></body></html>
```

  
Аналогично проводится проверка по числам  

```
$('.number').each(function () {    var cur = $(this);    cur.next().remove();    if (isNaN(cur.val())) {        cur.after('<span class="error"> Что-то не так</span>');        dataValid = false;    }});if (dataValid) {    $('#info').html('Все хорошо!');}
```
