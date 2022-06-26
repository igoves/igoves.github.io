---
title: "image-optimizer - php библиотека для сжатия и оптимизации изображений"
categories: 
  - "php"
---

Пример

```
    $factory = new \\ImageOptimizer\\OptimizerFactory();
    $optimizer = $factory->get();

    $filepath = /* path to image */;

    $optimizer->optimize($filepath);
    //optimized file overwrites original one
```

  
[https://github.com/psliwa/image-optimizer](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BzbGl3YS9pbWFnZS1vcHRpbWl6ZXI%3D)
