---
title: "Валидный Youtube в DLE"
categories: 
  - "xhtml"
tags: 
  - "data-life"
  - "dle"
  - "validaciya"
---

Ранее в посте [Пропорциональное масштабируемое видео и валидный youtube](https://dev.xfor.top/339-proporcionalnoe-masshtabiruemoe-video-i-validnyj-youtube.html) я привел код как выглядит валидный код ютуб плеера который отображается во всех браузерах.  
  
Теперь пойдет о мини хаке для ДЛЕ.  
  
Откройте **\\\\engine\\\\classes\\\\parse.class.php** на строчке где-то 540-овой найдите:  

```
return '<!--dle_youtube_begin:'.$url.'--><object width="'.$this->video_config['width'].'" height="'.$this->video_config['height'].'"><param name="movie" value="http://www.youtube.com/v/'.$video_link.'&hl=ru&fs=1"></param><param name="wmode" value="transparent" /><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed src="http://www.youtube.com/v/'.$video_link.'&hl=ru&fs=1" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" wmode="transparent" width="'.$this->video_config['width'].'" height="'.$this->video_config['height'].'"></embed></object><!--dle_youtube_end-->';
```

  
и замените на  

```
return '<!--dle_youtube_begin:'.$url.'--><!--[if IE]><object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" width="'.$this->video_config['width'].'" height="'.$this->video_config['height'].'"><param name="movie" value="http://www.youtube.com/v/'.$video_link.'&amp;hl=ru&amp;fs=1"></param><![endif]--><!--[if !IE]>--><object type="application/x-shockwave-flash" data="http://www.youtube.com/v/'.$video_link.'&amp;hl=ru&amp;fs=1" width="'.$this->video_config['width'].'" height="'.$this->video_config['height'].'"><!--<![endif]--><param name="wmode" value="transparent" /><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param></object><!--dle_youtube_end-->';
```

  
Теперь последующее новое видео с ютуба будет отображаться валидно!
