---
title: "mjaschen/phpgeo - простая гео библиотека на PHP"
categories: 
  - "php"
---

```
<?php

use Location\\Coordinate;
use Location\\Distance\\Vincenty;

$coordinate1 = new Coordinate(19.820664, -155.468066); // Mauna Kea Summit
$coordinate2 = new Coordinate(20.709722, -156.253333); // Haleakala Summit

echo $coordinate1->getDistance($coordinate2, new Vincenty()); // returns 128130.850 (meters; ?128 kilometers)
```

[https://github.com/mjaschen/phpgeo](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21qYXNjaGVuL3BocGdlbw%3D%3D)
