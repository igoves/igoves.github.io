---
title: "mpratt/Embera - php скрипт проверяет ссылки и если это embed ссылка, то конвертирует ее"
date: ""
categories: 
  - "php"
---

Поддерживает 60+ сайтов  
Пример использования  

```
$config = array(
        'params' => array(
            'width' => 300,
            'height' => 500
        )
    );

    $text = 'Check this video out http://vimeo.com/groups/shortfilms/videos/66185763';

    $embera = new \\Embera\\Embera($config);
    echo $embera->autoEmbed($text);

    /*Check this video out <iframe src="http://player.vimeo.com/video/66185763" width="300" height="480" ....*/
```

  
[https://github.com/mpratt/Embera](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21wcmF0dC9FbWJlcmE%3D)
