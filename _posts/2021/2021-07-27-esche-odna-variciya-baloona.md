---
title: "Еще одна вариция Baloon`a"
date: ""
categories: 
  - "js"
tags: 
  - "baloon"
---

![Еще одна вариция Baloon`a](images/1385318443_untitled-22.jpg "Еще одна вариция Baloon`a")

  

```
<!DOCTYPE html><html><head>    <style>        body {            font-family: Verdana;            font-size: .8em;            padding: 2em;        }                #message {            display: none;            width: 300px;            background: #EEEEEE;            border-radius: 6px;            box-shadow: 3px 3px 5px #B1B1B1;            padding: .1em 1.5em;            margin: .5em 0;        }                #toggle-link {            text-decoration: none;            border-bottom: 1px dashed;        }    </style>    <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.6.4/jquery.min.js"></script>    <script>        $(function() {            $('#toggle-link').click(function(e) {                var $message = $('#message');                                if ($message.css('display') != 'block') {                    $message.show();                                        var firstClick = true;                    $(document).bind('click.myEvent', function(e) {                        if (!firstClick && $(e.target).closest('#message').length == 0) {                            $message.hide();                            $(document).unbind('click.myEvent');                        }                        firstClick = false;                    });                }                                e.preventDefault();            });        });    </script></head><body>    <a href="#" id="toggle-link">Show message</a>    <div id="message">        <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.</p>    </div></body></html>
```

  
Предыдущий скрипт здесь [https://dev.xfor.top/510-baluuuuuun.html](https://dev.xfor.top/510-baluuuuuun.html)
