---
title: "JustClear/blurify - js для размытия изображения"
date: "2020-07-04"
categories: 
  - "js"
tags: 
  - "blur"
  - "images"
---

```
import blurify from 'blurify';

new blurify({
    images: document.querySelectorAll('.blurify'),
    blur: 6,
    mode: 'css',
});

// or in shorthand

blurify(6, document.querySelectorAll('.blurify'));
```

[https://github.com/JustClear/blurify](https://github.com/JustClear/blurify)
