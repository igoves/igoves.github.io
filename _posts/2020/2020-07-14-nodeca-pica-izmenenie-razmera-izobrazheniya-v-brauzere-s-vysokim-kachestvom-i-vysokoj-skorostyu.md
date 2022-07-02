---
title: "nodeca / pica - изменение размера изображения в браузере с высоким качеством и высокой скоростью"
date: "2020-07-14"
categories: 
  - "js"
tags: 
  - "images"
  - "resize"
---

```
const pica = require('pica')();

// Resize from Canvas/Image to another Canvas
pica.resize(from, to, {
  unsharpAmount: 80,
  unsharpRadius: 0.6,
  unsharpThreshold: 2
})
.then(result => console.log('resize done!'));

// Resize & convert to blob
pica.resize(from, to)
  .then(result => pica.toBlob(result, 'image/jpeg', 0.90))
  .then(blob => console.log('resized to canvas & created blob!'));
```

[https://github.com/nodeca/pica](https://github.com/nodeca/pica)
