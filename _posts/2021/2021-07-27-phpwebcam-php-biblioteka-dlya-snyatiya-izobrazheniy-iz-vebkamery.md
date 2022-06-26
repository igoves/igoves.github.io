---
title: "PhpWebcam - php библиотека для снятия изображений из вебкамеры"
categories: 
  - "php"
---

```
$webcam = new \\VDX\\Webcam\\Webcam();

// It can produce an other size if your webcam does not support the provided size
$webcam->setDesiredSize(1280, 720);

if ($webcam->open()) {
    $webcam->saveFrame('/tmp/test.jpg'/*, true*/); // It accepts a second parameter to mirror the image
    $webcam->close();
}
```

  
[https://github.com/vdechenaux/PhpWebcam](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3ZkZWNoZW5hdXgvUGhwV2ViY2Ft)
