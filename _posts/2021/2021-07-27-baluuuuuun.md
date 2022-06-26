---
title: "БАЛУН111!"
categories: 
  - "js"
tags: 
  - "-javascript"
  - "js"
  - "vozdushnyy-sharik"
---

![БАЛУН111!](images/1294596045_39.jpg "БАЛУН111!")

  
  
  
  
**JS**  

```
<script type="text/javascript"><!--var cur_balloon = '';var isvis = false;function Balloon_Off(){    if(isvis){ isvis = false; return; }    var Balloon = cur_balloon ? document.getElementById(cur_balloon) : '';    if (Balloon) { Balloon.style.display = 'none'; document.onclick = null; cur_balloon = '';  }}function Balloon_On(bid){    Balloon_Off();    var Balloon = document.getElementById(bid);    if (!Balloon) return;    cur_balloon = bid;    Balloon.style.display = '';    isvis = true;    document.onclick = Balloon_Off;    Balloon.onclick = new Function("isvis=true");    return false;}//--></script>
```

  
  
**CSS**  

```
<style>a {position:absolute; top:30%; left:50%; margin-left:-100px; display:block; text-decoration:none; border-bottom:1px dashed; font-size:16px;}a:hover {border-bottom:0px;}#Form {width:200px; height:300px; background:#eee; border:1px solid #B7B7B5; -moz-border-radius:15px; -webkit-border-radius:15px; border-radius: 15px; text-align:center; padding-top:40px;}</style>
```

  
  
**HTML**  

```
<a href="#" onclick="return Balloon_On('Form')">Жмякнуть в эту штуку</a><div id="Form" style="display:none; position:absolute; top:20%; left:70%; margin-left:-100px;">А здесь блок</div>
```
