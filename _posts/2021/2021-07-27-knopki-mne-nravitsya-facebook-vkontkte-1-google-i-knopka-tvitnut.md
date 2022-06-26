---
title: "Кнопки Мне нравится - Facebook & Vkontkte, +1 Google и кнопка Твитнуть"
categories: 
  - "note"
tags: 
  - "gugl-plyus-odin"
  - "layki"
  - "mne-nravitsya"
  - "tvitnut"
---

От сегодня в [подробном](https://dev.xfor.top/617-knopki-mne-nravitsya-facebook-vkontkte-1-google-i-knopka-tvitnut.html) описании поста появились кнопки:  

  
Вот так выглядит код на этом сайте:  
В шапке (между тегами head):  

```
<script type="text/javascript" src="http://userapi.com/js/api/openapi.js?31"></script><script type="text/javascript">  VK.init({apiId: 2258801, onlyWidgets: true});</script><script type="text/javascript" src="http://apis.google.com/js/plusone.js">  {lang: 'ru', parsetags: 'explicit'}</script>
```

  
  
В месте где сами кнопки:  

```
<div style="float:left"><div id="fb-root"></div></div><div style="float:left"><a href="http://twitter.com/share" class="twitter-share-button" data-count="horizontal" data-via="igor_veselov" data-lang="ru">Tweet</a></div><div style="float:left"><g:plusone size="medium"></g:plusone></div><div style="float:left"><div id="vk_like"></div></div><script type="text/javascript" src="http://platform.twitter.com/widgets.js"></script><script type="text/javascript">gapi.plusone.go();</script><script src="http://connect.facebook.net/ru_RU/all.js#xfbml=1"></script><fb:like href="" send="true" layout="button_count" width="250" show_faces="true" font="tahoma"></fb:like><script type="text/javascript">VK.Widgets.Like("vk_like", {type: "button"});</script>
```
