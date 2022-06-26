---
title: "Ticker`ы на jQuery"
categories: 
  - "js"
---

```
<script>    function tick(){        $('#ticker_01 li:first').slideUp( function () { $(this).appendTo($('#ticker_01')).slideDown(); });    }    setInterval(function(){ tick () }, 5000);    function tick2(){        $('#ticker_02 li:first').slideUp( function () { $(this).appendTo($('#ticker_02')).slideDown(); });    }    setInterval(function(){ tick2 () }, 3000);    function tick3(){        $('#ticker_03 li:first').animate({'opacity':0}, 200, function () { $(this).appendTo($('#ticker_03')).css('opacity', 1); });    }    setInterval(function(){ tick3 () }, 4000);        function tick4(){        $('#ticker_04 li:first').slideUp( function () { $(this).appendTo($('#ticker_04')).slideDown(); });    }    /**     * USE TWITTER DATA     */     $.ajax ({         url: 'http://search.twitter.com/search.json',         data: 'q=%23javascript',         dataType: 'jsonp',         timeout: 10000,         success: function(data){             if (!data.results){                 return false;             }             for( var i in data.results){                 var result = data.results[i];                 var $res = $("<li />");                 $res.append('<img src="' + result.profile_image_url + '" />');                 $res.append(result.text);                 console.log(data.results[i]);                 $res.appendTo($('#ticker_04'));             }            setInterval(function(){ tick4 () }, 4000);                $('#example_4').show();         }    });</script>
```

  
[РЕЗУЛЬТАТ](https://dev.xfor.top/go/aHR0cDovL3dvcmtzaG9wLnJzL2RlbW8vbmV3cy10aWNrZXItaW4tNC1saW5lcy8%3D)
