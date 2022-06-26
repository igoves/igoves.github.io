---
title: "JS движущийся блок противоположно курсору"
categories: 
  - "js"
---

![JS движущийся блок противоположно курсору](images/1418159480_untitled-2.png "JS движущийся блок противоположно курсору")

  

```
<!DOCTYPE html><html class="no-js">    <head>        <meta charset="utf-8">        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">        <title></title>        <meta name="description" content="">        <meta name="viewport" content="width=device-width, initial-scale=1">    </head>    <body id="b_sh"  style="background:#eee; position:relative;">        <div 			style="				position:absolute; 				font-size:90px; 				top:100px; 				left:200px; 				padding:20px; 				background:#fff;				width:200px;				height:200px;			"		>			1		</div>        <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>		<script>		$('body').mousemove(function(e){			var amountMovedX = (e.pageX * +11 / 60)-33;			var amountMovedY = (e.pageY * +11 / 60)-30;			$('#b_sh').css('bottom', amountMovedY + 'px');			$('#b_sh').css('right', amountMovedX + 'px');		});		</script>    </body></html>
```

  
[http://jsfiddle.net/n78jkhdp/](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9uNzhqa2hkcC8%3D)
