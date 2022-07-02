---
title: "josh.js - библиотека JavaScript для анимации содержимого при прокрутке страницы."
date: "2020-09-04"
categories: 
  - "js"
tags: 
  - "animation"
  - "scroll"
---

HTML

```
<div
    class="element josh-js"
    data-josh-anim-name="lightSpeedInRight"
    data-josh-duration="1500ms"
    data-josh-anim-delay="3.5s"
    data-josh-iteration="infinite"
>
    Written on ES6
</div>
```

JS

```
const josh = new Josh({
    // DOM CSS class to Animate, default is "josh-js"
    initClass: "josh-js",

    // Animation CSS class from Animate.css library
    animClass: "animate__animated",

    // Element distance of viewport to triggering the animation. default is 0.2 means 20% of element view animation will trigger
    offset: 0.2,

    // Animation will trigger on Mobile or not. Default is true
    animateInMobile: true,

    // Animation will trigger on newly added element or not. Default is false
    onDOMChange: false,
  });
```

[https://github.com/mamunhpath/josh.js](https://github.com/mamunhpath/josh.js)
