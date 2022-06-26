---
title: "POST через AJAX"
categories: 
  - "xhtml"
tags: 
  - "ajax"
  - "post"
  - "ayaks"
  - "zapros"
---

POST это тот же GET только параметры передаются скрыто, поэтому формировать строку нужно самому (function get).  
  
**ajax**:  

```
var http_request = false;   function makePOSTRequest(url, parameters) {      http_request = false;      if (window.XMLHttpRequest) { // Mozilla, Safari,...         http_request = new XMLHttpRequest();         if (http_request.overrideMimeType) {            http_request.overrideMimeType('text/html');         }      } else if (window.ActiveXObject) { // IE         try {            http_request = new ActiveXObject("Msxml2.XMLHTTP");         } catch (e) {            try {               http_request = new ActiveXObject("Microsoft.XMLHTTP");            } catch (e) {}         }      }      if (!http_request) {         alert('Cannot create XMLHTTP instance');         return false;      }      http_request.onreadystatechange = alertContents;      http_request.open('POST', url, true);      http_request.setRequestHeader("Content-type", "application/x-www-form-urlencoded");      http_request.setRequestHeader("Content-length", parameters.length);      http_request.setRequestHeader("Connection", "close");      http_request.send(parameters);   }   function alertContents() {      if (http_request.readyState == 4) {         if (http_request.status == 200) {            result = http_request.responseText;            document.getElementById('myspan').innerHTML = result;                     } else {            alert('There was a problem with the request.');         }      }   }      function get(obj) {      var poststr = "usr=" + encodeURI( document.getElementById("usr").value ) + "&pass=" + encodeURI( document.getElementById("pass").value );      makePOSTRequest('post.php', poststr);   }
```

  
вызывается:  

```
<form action="javascript:get(document.getElementById('myform'));" name="myform" id="myform"><input name="usr" id="usr" type="text" size="10" maxlength="10" /><br/><br/><input name="pass" id="pass" type="text" size="10" maxlength="10" /><br/><br/><input type="button" name="button" value="Submit" onclick="javascript:get(this.parentNode);"></form>
```

  
пост обработчик:  

```
<?print_r($_POST);?>
```

  
[ДЕМО POST](https://dev.xfor.top/uploads/files/demo/016/index.html)
