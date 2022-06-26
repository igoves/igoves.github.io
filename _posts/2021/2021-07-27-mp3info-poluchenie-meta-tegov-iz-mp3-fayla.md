---
title: "Mp3Info - получение мета тегов из mp3 файла"
date: ""
categories: 
  - "php"
---

```
use wapmorgan\\Mp3Info\\Mp3Info;
$audio = new Mp3Info($fileName, true);
// or omit 2nd argument to increase parsing speed
$audio = new Mp3Info($fileName);
echo 'Audio duration: '.floor($audio->duration / 60).' min '.floor($audio->duration % 60).' sec'.PHP_EOL;
echo 'Audio bitrate: '.($audio->bitRate / 1000).' kb/s'.PHP_EOL;
```

  
[https://github.com/wapmorgan/Mp3Info](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dhcG1vcmdhbi9NcDNJbmZv)
