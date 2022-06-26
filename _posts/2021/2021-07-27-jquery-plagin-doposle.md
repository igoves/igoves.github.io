---
title: "jQuery плагин До/После"
categories: 
  - "js"
tags: 
  - "jquery"
---

[![jQuery плагин До/После](images/1280309682_123.jpg "jQuery плагин До/После")](https://dev.xfor.top/wp-content/uploads/posts/2010-07/1280309682_123.jpg)

  
[Демо](https://dev.xfor.top/go/aHR0cDovL3d3dy5jYXRjaG15ZmFtZS5jb20vanF1ZXJ5L2RlbW8vOC8%3D)  
  
**Скачать**  
[Download jquery.beforeafter.zip](https://dev.xfor.top/go/aHR0cDovL3d3dy5jYXRjaG15ZmFtZS5jb20vanF1ZXJ5L2pxdWVyeS5iZWZvcmVhZnRlci56aXA%3D)  
  
Подключается:  

```
<div id="container"> <div><img alt="before" src="before.jpg" width="600" height="366" /></div> <div><img alt="after" src="after.jpg" width="600" height="366" /></div></div>
```

  

```
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.3.2/jquery.min.js"></script><script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jqueryui/1.7.1/jquery-ui.min.js"></script><script type="text/javascript" src="jquery.beforeafter.js"></script><script type="text/javascript">$(function(){    $('#container').beforeAfter();});</script>
```

  
Опции:  
**animateIntro** – whether or not to have the drag bar start completely to the right of the container and gradually move by itself to the midpoint (default false)  
**introDelay** – if animateIntro is true, the number of milliseconds to wait before beginning the automatic drag bar move to the center of the image (default 1000)  
**introDuration** – if animateIntro is true, the number of milliseconds it will take for the drag bar to go from the right side of the image to the middle of the image (default 1000)  
**showFullLinks** – whether or not to display links below the image that a visitor can click on that will automatically show the full before or full after image (default true)  
**imagePath** – the path (absolute or relative) to where you store the navigation images (default ‘/js/beforeAfter/’)  
  
Как-то так:  

```
$('#container').beforeAfter({    animateIntro : true,        introDelay : 2000,        introDuration : 500,        showFullLinks : false});
```
