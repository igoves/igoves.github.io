---
title: "difference - php скрипт высчитывающий разницу между изображениями"
date: ""
categories: 
  - "php"
---

```
use Undemanding\\Difference\\Image;
use Undemanding\\Difference\\Method\\EuclideanDistance;

$image1 = new Image("/path/to/image1.png");
$image2 = new Image("/path/to/image2.png");

$difference = $image1->difference($image2, new EuclideanDistance());

$boundary = $difference->boundary(); // ? ["left" => ..., "top" => ...]
$percentage = $difference->percentage(); // ? 14.03...
```

  
[https://github.com/undemanding/difference](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3VuZGVtYW5kaW5nL2RpZmZlcmVuY2U%3D)
