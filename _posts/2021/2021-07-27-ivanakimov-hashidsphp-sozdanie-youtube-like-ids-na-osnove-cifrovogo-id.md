---
title: "ivanakimov/hashids.php - создание YouTube-like ids на основе цифрового id"
date: ""
categories: 
  - "php"
---

```
use Hashids\\Hashids;

$hashids = new Hashids();

$id = $hashids->encode(1, 2, 3); // o2fXhV
$numbers = $hashids->decode($id); // [1, 2, 3]
```

  
[https://github.com/ivanakimov/hashids.php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2l2YW5ha2ltb3YvaGFzaGlkcy5waHA%3D)
