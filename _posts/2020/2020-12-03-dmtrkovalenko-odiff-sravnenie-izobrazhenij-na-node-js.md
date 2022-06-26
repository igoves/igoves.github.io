---
title: "dmtrKovalenko/odiff - сравнение изображений на node.js"
date: "2020-12-03"
categories: 
  - "js"
tags: 
  - "diff"
  - "image"
---

![](https://res.cloudinary.com/xfor/images/w_1024,h_394/v1606758919/download-1/download-1.png?_i=AA)

```
const { compare } = require("odiff-bin");

const { match, reason } = await compare(
  "path/to/first/image.png",
  "path/to/second/image.png",
  "path/to/diff.png"
);
```

[https://github.com/dmtrKovalenko/odiff](https://github.com/dmtrKovalenko/odiff)
