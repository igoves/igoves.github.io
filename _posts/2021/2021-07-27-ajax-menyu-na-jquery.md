---
title: "Ajax меню на jQuery"
categories: 
  - "js"
---

```
$('body').on('click', '.some-menu .somelink', function(e){     var myUrl = $(e.target).attr('href');     var myTargetBlock = $(e.target).attr('target');     var myQueryBlock = $(e.target).attr('query');     $(myTargetBlock).load(myUrl+' '+response myQueryBlock );     $('.somelink.active').removeClass('active');     $(e.target).addClass('active');     history.pushState('', '', myUrl);});
```

  

```
<ul class="some-menu"> <li>   <a href="/somepage" target="#this-page-content-wrapper" query="this-page-content">bla bla bla</a> </li></ul>
```
