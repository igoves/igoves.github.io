---
title: "Airport – эффект информационной доски с помощью JQuery"
date: ""
categories: 
  - "js"
tags: 
  - "airport"
  - "jquery"
---

![Airport – эффект информационной доски с помощью JQuery](images/1307879115_12365860452a6mry.jpg "Airport – эффект информационной доски с помощью JQuery")

  
Такой эффект можно увидеть на информационных досках в аэропортах и вокзалах.  

```
<p>I like <span id="stuff"></span></p>       <script src="jquery-1.2.6.min.js" type="text/javascript" charset="utf-8"></script>        <script src="jquery.airport-1.1.js" type="text/javascript" charset="utf-8"></script>        <script type="text/javascript">            // <![CDATA[                $(document).ready(function(){                                $('#stuff').airport(['berlin','odessa','melbourne','moscow']);            });                // ]]>        </script>
```

  
[ДЕМО](https://dev.xfor.top/go/aHR0cDovL3NhbmRib3gudW53cm9uZ2VzdC5jb20vanF1ZXJ5LmFpcnBvcnQv) / [СКАЧАТь](https://dev.xfor.top/go/aHR0cDovL2pxdWVyeS1haXJwb3J0Lmdvb2dsZWNvZGUuY29tL2ZpbGVzL2pxdWVyeS5haXJwb3J0LTEuMS5zb3VyY2UuanM%3D)  
Этот плагин прост в использовании, думаю, ни у кого не возникнет проблем с ним, а если и возникнет проблема, тогда пишите в комментарии.
