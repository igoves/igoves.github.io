---
title: "Делаем бокс со счетчиком символов и визуальным баром на jQuery"
date: ""
categories: 
  - "js"
---

![Делаем бокс со счетчиком символов и визуальным баром на jQuery](images/1333794020_untitled-1.jpg "Делаем бокс со счетчиком символов и визуальным баром на jQuery")

  
**JS**  

```
 $(document).ready(function(){$("#contentbox").keyup(function(){var box=$(this).val();var main = box.length *100;var value= (main / 145);var count= 145 - box.length;if(box.length <= 145){$('#count').html(count);$('#bar').animate({"width": value+'%',}, 1);}else{alert('Full');}return false;});});
```

  
CSS  

```
body{font-family:Arial, Helvetica, sans-serif;}#contentbox{width:450px; height:50px;border:solid 2px #006699;font-family:Arial, Helvetica, sans-serif;font-size:14px;}#button{background-color:#006699;color:#ffffff;font-size:13px;font-weight:bold;padding:4px;}#cancel{background-color:#dedede;color:#000;font-size:13px;padding:4px;margin-left:10px;}#button_block{display:none;}#bar{background-color:#5fbbde;width:0px;height:16px;}#barbox{float:right; height:16px; background-color:#FFFFFF; width:100px; border:solid 2px #000; margin-right:3px;-webkit-border-radius:5px;-moz-border-radius:5px;}#count{float:right; margin-right:8px; font-family:'Georgia', Times New Roman, Times, serif; font-size:16px; font-weight:bold; color:#666666}
```

  
**HTML**  

```
<div id="barbox"><div id="bar"></div></div><div id="count">145</div></div><textarea id="contentbox"></textarea><div id="button_block"><input type="submit" id="button" value=" Share "/><input type="submit" id='cancel' value=" cancel"  /></div>
```
