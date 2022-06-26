---
title: "threesixty.js - transforms image sprite into 360 image view"
date: "2021-04-14"
categories: 
  - "js"
tags: 
  - "360"
  - "image-view"
---

![](https://camo.githubusercontent.com/d6578f930c9140cb567738b5f03d04a2b303fc5ce2639d2230a602477be8ca3a/68747470733a2f2f73332e65752d63656e7472616c2d312e616d617a6f6e6177732e636f6d2f746872656573697874792e6a732f73616d706c652e676966)

Vanilla js, no dependancies. Example:

```
const threesixty = new ThreeSixty(document.getElementById('threesixty'), {
  image: 'images/example.jpg',
  count: 19,
  perRow: 4,
  prev: document.getElementById('prev'),
  next: document.getElementById('next')
});

threesixty.play();
```

[https://github.com/mladenilic/threesixty.js](https://github.com/mladenilic/threesixty.js)
