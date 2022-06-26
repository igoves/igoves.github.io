---
title: "spatie/image-optimizer - оптимизация изображений на PHP"
categories: 
  - "php"
---

```
use Spatie\\ImageOptimizer\\OptimizerChainFactory;

$optimizerChain = OptimizerChainFactory::create();

$optimizerChain->optimize($pathToImage);
```

  
Оптимизирует PNGs, JPGs, SVGs и GIFs. Проходит цепочку инструментов JpegOptim, Optipng, Pngquant 2, SVGO, Gifsicle. Есть пакет для Laravel.  
[https://github.com/spatie/image-optimizer](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NwYXRpZS9pbWFnZS1vcHRpbWl6ZXI%3D)
