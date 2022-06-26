---
title: "Скрипт выезжающей панели снизу при прокрутке"
categories: 
  - "js"
tags: 
  - "niz"
  - "panel"
  - "tizer"
---

![Скрипт выезжающей панели снизу при прокрутке](images/1349702588_untitled-2.jpg "Скрипт выезжающей панели снизу при прокрутке")

  

```
<!DOCTYPE html> <html><head>	<meta charset="utf-8" />	<title>Скрипт</title>	<script src="http://yandex.st/jquery/1.7.2/jquery.min.js"></script></head><body><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><style>.linked {border:0px solid #ccc;background:#fff;-webkit-border-top-right-radius: 10px;-webkit-border-bottom-right-radius: 10px;-moz-border-radius-topright: 10px;-moz-border-radius-bottomright: 10px;border-top-right-radius: 10px;border-bottom-right-radius: 10px;-webkit-box-shadow: 1px 1px 7px rgba(50, 50, 50, 0.75);-moz-box-shadow:    1px 1px 7px rgba(50, 50, 50, 0.75);box-shadow:         1px 1px 7px rgba(50, 50, 50, 0.75);}.close {text-decoration:none; color:#999;}.linked{position:fixed;left:-340px;bottom:25px;width:340px;text-align:left;z-index:100;display:none}.linked table{width:100%}.linked .top-c{height:30px;}.linked .top-r{height:30px;width:30px;}.linked .mid-c{background:#fff;padding:0px 0px 0px 10px}.linked .mid-r{width:30px;}.linked .bot-r{height:30px;width:30px;}.linked .bot-c{height:30px;}.linked .close{width:18px;height:18px;position:absolute;right:30px;top:30px;display:block}</style><script>var isLoadObozrevatelCommonJS = true;var linked ={    show: true,    Hide: function() {        $(".linked").animate({ left: -340 }, 200, function() { $(this).hide() });    },    Init: function() {        $(".linked .close").click(function() {            linked.show = false;            linked.Hide();            return false;        });        linked.startShow = $(".read-also").offset().top;        $(window).scroll(function() {            if (!linked.show)                return;            var scroll = $(document).scrollTop();            var obj = $(".linked");            if (scroll + window.innerHeight > linked.startShow + $(".linked").height()) {                if (!obj.is(':visible') && !obj.is(':animated')) {                    $(".linked").show().animate({ left: 0 }, 200);                }            } else {                if (obj.is(':visible') && !obj.is(':animated')) {                    linked.Hide();                }            }        });    }}</script><script>InitNewsScroll()</script>		<div class="read-also"></div><div class="linked">    <table cellpadding="0" cellspacing="0" border="0">        <tr><td></td><td class="top-r"></td></tr>        <tr>            <td class="mid-c">				asdfasf            </td>            <td class="mid-r"></td>        </tr>        <tr><td class="bot-c"></td><td class="bot-r"></td></tr>    </table>    <a class="close" href="#">x</a></div><script>linked.Init()</script><div style="width:100px; height:100px; background:grey"></div></body></html>
```
