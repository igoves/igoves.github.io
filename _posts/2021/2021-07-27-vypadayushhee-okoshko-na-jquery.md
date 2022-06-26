---
title: "Выпадающее окошко на jquery"
categories: 
  - "css"
tags: 
  - "jquery"
  - "vypadayueshchee"
  - "okno"
---

![Выпадающее окошко на jquery](images/1275464578_untitled-1.jpg "Выпадающее окошко на jquery")

  
За выпадение отвечает:  

```
$(function(){    $('#contacts_opener').click(function(){        $('#contacts_block').css('display', 'block');        $('#contacts_block').animate({top: 100}, 400, 'swing');    });        $('#contacts_closer').click(function(){        $('#contacts_block').animate({top: -500}, 400, 'swing', function(){$('#contacts_block').css('display', 'none')});    });        $('#select_quest').click(function(){        $('#physic_addr').hide();        $('#virtual_addr').fadeIn();    });        $('#select_addr').click(function(){        $('#virtual_addr').hide();        $('#physic_addr').fadeIn();    });        $('.otz_pic').hover(function(){        $(this).css('border','1px solid #e07824');    }, function(){        $(this).css('border','1px solid #cccccc');    });        setInterval('tr()', 150);    setInterval('photos()', 800);});
```

  
[Демо](https://dev.xfor.top/go/aHR0cDovL3Zlc2Vsb3Yuc3VteS51YS91cGxvYWRzL2ZpbGVzL2RlbW8vMDE4L2luZGV4Lmh0bWw%3D) | [Скачать](https://dev.xfor.top/go/aHR0cDovL3Zlc2Vsb3Yuc3VteS51YS91cGxvYWRzL2ZpbGVzL2RlbW8vMDE4L2FyY2hpdmUucmFy)
