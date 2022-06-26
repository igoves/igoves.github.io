---
title: "Переводчик на jquery (jquery-translate)"
categories: 
  - "js"
tags: 
  - "google-api"
  - "jq"
  - "jqery-cookie"
  - "jquery"
  - "jsapi"
  - "translate"
---

![Переводчик на jquery (jquery-translate)](images/1294597162_44.jpg "Переводчик на jquery (jquery-translate)")

  
Есть такой сайт [http://edo.webmaster.am/gtranslate](https://dev.xfor.top/go/aHR0cDovL2Vkby53ZWJtYXN0ZXIuYW0vZ3RyYW5zbGF0ZQ%3D%3D)  
Так вот там есть скрипт под названием **gtranslate**, который позволяет переводить сайт или отдельные блоки сайта на разные языки используя google translate api (Там же и конструктор построения блока переводчика). В связке с jquery cookie он еще и запонимает переменную(glang) языка на какую нужно переводить. И выглядит это так:  
  
  
  

```
<a href="javascript:doGTranslate('ru|en')" title="English" class="gflag" style="background-position:-0px -0px;"> Перевести на инглиш -) </a><script type="text/javascript" src="http://www.google.com/jsapi"></script><script type="text/javascript">google.load("jquery", "1.4.2");</script><script type="text/javascript" src="http://joomla-gtranslate.googlecode.com/svn/trunk/mod_gtranslate/jquery-translate.js"></script><script type="text/javascript">//<![CDATA[if(jQuery.cookie('glang') && jQuery.cookie('glang') != 'ru') jQuery(function($){$('body').translate('ru', $.cookie('glang'), {toggle:true, not:'.notranslate'});});function doGTranslate(lang_pair) {if(lang_pair.value)lang_pair=lang_pair.value;var lang=lang_pair.split('|')[1];jQuery.cookie('glang', lang, {path: '/'});jQuery(function($){$('body').translate('ru', lang, {toggle:true, not:'.notranslate'});});}//]]></script>
```
