---
title: "jQuery сниппеты: изменение высоты iframe в зависимости от его содержания"
categories: 
  - "js"
---

```
<script type="text/javascript">$(function() {    var iframe = $('#ourframe', parent.document.body);    iframe.height($(document.body).height());});</script>
```

  

```
<html>    ...    <body>        <iframe id="ourframe"></iframe>    </body>    ...</html>
```
