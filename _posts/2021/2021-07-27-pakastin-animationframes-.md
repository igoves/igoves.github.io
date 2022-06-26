---
title: "pakastin/animationframes - скрипт создания анимации на js"
date: ""
categories: 
  - "js"
---

```
import { frames, ease } from 'animationframes';

const translate = (x, y) => `translate(${x}%, ${y}%)`;

const el = document.createElement('h1');

const animation = frames(0, 1000)
  .start(() => {
    el.style.transform = translate(-100, 0);
  })
  .progress((t) => {
    const e = ease.quartInOut(t);
    const x = -100 * (1 - e);

    el.style.transform = translate(x, 0);
  })
  .end(() => {
    el.style.transform = '';
  });

el.textContent = 'Hello world!';

document.body.appendChild(el);
```

  
[https://github.com/pakastin/animationframes](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Bha2FzdGluL2FuaW1hdGlvbmZyYW1lcw%3D%3D)
