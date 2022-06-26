---
title: "Imagery - php обертка для GD"
categories: 
  - "php"
---

Умеет ресайзить, кропать, перевораивать и вращать, создание коллажей, фильтры и эффекты.  
Пример открытия файла  

```
$image = Imagery::open($filename); - from a file.
$image = Imagery::create($width, $height); - new image
$image = new Imagery(imagecreatefrombmp('image.bmp')); - from a resource
```

  
[https://github.com/wapmorgan/Imagery](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dhcG1vcmdhbi9JbWFnZXJ5)
