---
title: "ImageHash - библиотека на php вычисляющая хеш изображения"
categories: 
  - "php"
---

Пример использования  

```
use Jenssegers\\ImageHash\\ImageHash;

$hasher = new ImageHash;
$hash = $hasher->hash('path/to/image.jpg');
```

  
Так же можно рассчитать дистанцию между двумя изображениями (с погрешностями), тем самым определить это одно и то же изображение или нет  

```
$distance = $hasher->distance($hash1, $hash2);
```

  
[https://github.com/jenssegers/imagehash](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2plbnNzZWdlcnMvaW1hZ2VoYXNo)
