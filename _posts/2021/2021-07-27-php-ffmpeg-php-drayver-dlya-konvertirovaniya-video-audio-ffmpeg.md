---
title: "PHP-FFMpeg - PHP драйвер для конвертирования  видео аудио FFMpeg"
date: ""
categories: 
  - "php"
---

Пример

```
$ffmpeg = FFMpeg\\FFMpeg::create();
$video = $ffmpeg->open('video.mpg');
$video
    ->filters()
    ->resize(new FFMpeg\\Coordinate\\Dimension(320, 240))
    ->synchronize();
$video
    ->frame(FFMpeg\\Coordinate\\TimeCode::fromSeconds(10))
    ->save('frame.jpg');
$video
    ->save(new FFMpeg\\Format\\Video\\X264(), 'export-x264.mp4')
    ->save(new FFMpeg\\Format\\Video\\WMV(), 'export-wmv.wmv')
    ->save(new FFMpeg\\Format\\Video\\WebM(), 'export-webm.webm');
```

  
[https://github.com/PHP-FFmpeg/PHP-FFmpeg/](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1BIUC1GRm1wZWcvUEhQLUZGbXBlZy8%3D)
