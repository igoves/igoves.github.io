---
title: "lovell/sharp - процессор картинок для node.js"
date: ""
categories: 
  - "js"
---

Умеет работать с JPEG, PNG и WebP. В 4 раза быстрей чем GraphicsMagick  

```
const roundedCorners = Buffer.from(
  '<svg><rect x="0" y="0" width="200" height="200" rx="50" ry="50"/></svg>'
);

const roundedCornerResizer =
  sharp()
    .resize(200, 200)
    .overlayWith(roundedCorners, { cutout: true })
    .png();

readableStream
  .pipe(roundedCornerResizer)
  .pipe(writableStream);
```

  
[https://github.com/lovell/sharp](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2xvdmVsbC9zaGFycA%3D%3D)
