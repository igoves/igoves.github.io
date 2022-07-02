---
title: "Пропорциональное масштабируемое видео и валидный youtube"
categories: 
  - "css"
tags: 
  - "youtube"
  - "video"
---

Пропорциональное масштабируемое реализовано за счет позиционирования блоков и процентных соотношений. Применимо на резиновых сайтах.  
**CSS**  

```
#containingBlock {  width:50%;}.videoWrapper {  position: relative;  padding-bottom:56.25%;  padding-top:25px;  height:0;  overflow:hidden;}.videoWrapper div,.videoWrapper object {  position:absolute;  top:0;  left:0;  width: 100%;  height:100%;}
```

  
Код видео с ютуба по умолчанию не валидный, здесь же он добавлен в соответствии стандартам  
  
**HTML**  

```
<div id="containingBlock">  <div class="videoWrapper">    <div>      <!--[if IE]>      <object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" width="480" height="295">        <param name="movie" value="http://www.youtube.com/v/mDRYnaajUcY&amp;hl=en&amp;fs=1&amp;showinfo=0" />      <![endif]-->      <!--[if !IE]>-->      <object type="application/x-shockwave-flash" data="http://www.youtube.com/v/mDRYnaajUcY&amp;hl=en&amp;fs=1&amp;showinfo=0" width="480" height="295">      <!--<![endif]-->        <param name="quality" value="high" />        <param name="wmode" value="opaque" />        <p><a href="http://www.adobe.com/go/getflashplayer"><img alt="Get Adobe Flash player" src="http://www.adobe.com/images/shared/download_buttons/get_flash_player.gif"/></a></p>      </object>    </div>    <p>Following is the description of the video embeded in this document</p>    <p>This short clip is about YouTube widescreen formatting. It shows the two main formats (16:9, 4:3) and also explains the best way to create a Flash movie according to the new widescreen format.</p>  </div>  ...</div>
```

  
Очень мне нравится девочка с видео демки -)  
  
ДЕМО: [https://dev.xfor.top/uploads/files/demo/003/index.html](https://dev.xfor.top/go/aHR0cDovL3Zlc2Vsb3Yuc3VteS51YS91cGxvYWRzL2ZpbGVzL2RlbW8vMDAzL2luZGV4Lmh0bWw%3D)
