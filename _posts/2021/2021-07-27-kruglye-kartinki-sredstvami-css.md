---
title: "Круглые картинки средствами CSS"
categories: 
  - "css"
---

![Круглые картинки средствами CSS](images/1322852607_untitled-1.jpg "Круглые картинки средствами CSS")

  

```
<span class="frame"><img src="http://seangaffney.cc/new/img/me.jpg" /></span><span class="frame"><img src="http://a3.twimg.com/profile_images/1136130947/twitter-dribbble-profile-pic_reasonably_small.png" /></span><span class="frame"><img src="http://a3.twimg.com/profile_images/1100546975/Screen_shot_2010-08-11_at_9.08.03_AM_reasonably_small.png" /></span><span class="frame"><img src="http://a2.twimg.com/profile_images/935982818/avatar_main_copy_square_reasonably_small.jpg" /></span>
```

  

```
body{background:#333; padding:10em;}.frame{    display:inline-block;    position:relative;    overflow:hidden;}.frame>img{    vertical-align:top;}.frame, .frame:before{    -moz-border-radius:100em;    border-radius:100em;    }.frame>img{    -webkit-border-radius:100em;   }.frame:before{    content:'';    display:block;    position:absolute;    left:0;    right:0;    width:100%;    height:100%;    margin:-10em;    border:10em solid #333;}
```

  
[Смотреть](http://jsfiddle.net/rogie/GnuXw/)
