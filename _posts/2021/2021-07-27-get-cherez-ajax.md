---
title: "GET через AJAX"
categories: 
  - "xhtml"
tags: 
  - "ajax"
  - "get"
  - "js"
  - "dannye"
---

То что **AJAX** заменит все и вся врядле, но то что он стал уже необходимым атрибутом в вебе это факт. В посте пойдет речь о простой отправке данных через **GET** запрос используя **AJAX**.  
  
**index.html**  

```
<html><head><meta content="text/html; charset=utf-8" http-equiv="content-type" /><title>GET AJAX</title><script src="ajax.js" type="text/javascript"></script></head><body><strong>Введите какой-нибудь текст латинницой</strong><br><input name="getparam" type="text" size="10" id="input" maxlength="15"><div id="show"> </div></body></html>
```

  
  
**ajax.js**  

```
window.onload = initAll; /*При завершении загрузки запустить функцию initAll*/var xmlhttp = false;var outputtext = "";function initAll() {document.getElementById("input").addEventListener('keyup',startAjax,false);/*Добавляем слушателя событий для текстого поля в файле index.html*/}function startAjax(){if (window.XMLHttpRequest) {xmlhttp = new XMLHttpRequest();}else {if (window.ActiveXObject) {xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");}}var url = "a.php?module="+this.value;/*создаем переменую урла и добавляем вконце новое значение текстого поля при помощи this.value*/xmlhttp.onreadystatechange = checking;xmlhttp.open("GET",url,true);xmlhttp.send(null);}function checking(){if (xmlhttp.readyState == 4) {if (xmlhttp.status == 200) {outputtext = xmlhttp.responseText;}else {outputtext = "Ошибка: " + xmlhttp.status;}}document.getElementById("show").innerHTML = outputtext; /*Вывод данных с a.php в елемент div c id="show"*/}
```

  
  
**a.php**  

```
<?phpif(isset($_GET['module'])){echo "Обработка <strong>GET</strong> в файле a.php прошла успешно: <b>".$_GET['module']."</b> <br><br>Обращение произошло по адрессу: /a.php?module=".$_GET['module'];}?>
```

  
[ДЕМО](https://dev.xfor.top/uploads/files/demo/015/index.html)
