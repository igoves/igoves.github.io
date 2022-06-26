---
title: "css вынести блок за пределы overflow"
categories: 
  - "css"
---

![css вынести блок за пределы overflow](images/1403944436_untitled-1.png "css вынести блок за пределы overflow")

  

```
<div class="wrap1">	<div class="wrap2">			Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod		<div class="flying">hello</div>		tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodoconsequat. Duis aute irure dolor in reprehenderit in voluptate velit essecillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat nonproident, sunt in culpa qui officia deserunt mollit anim id est laborum.	</div></div>
```

```
.wrap1 {	width: 200px;	height: 200px;	position: relative;	border: 1px solid;}.wrap2 {	width: 100%;	height: 100%;	overflow: hidden;}.flying {	position: absolute;	left: 200px;	background: lime;	padding: 20px;}
```

  
[Смотреть результат](https://dev.xfor.top/go/aHR0cDovL2RhYmJsZXQuY29tL2dpc3QvNzcyOTU2MA%3D%3D)
