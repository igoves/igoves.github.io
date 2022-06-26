---
title: "Абсолютный центр"
date: "2009-10-03"
categories: 
  - "note"
tags: 
  - "verstka"
  - "div"
  - "centr"
---

Допустим нам надо ровно по середине блок height:600px; width:900px; Реализуется это очень просто:

```
<style>
.center {
position:absolute;
top:50%;
left:50%;
height:600px;
width:900px;
margin-top:-300px;
margin-left:-450px;
</style>

<div class="center">
Этот блок кросс да еще и ровно по центру УхУХ!
</div>
```
