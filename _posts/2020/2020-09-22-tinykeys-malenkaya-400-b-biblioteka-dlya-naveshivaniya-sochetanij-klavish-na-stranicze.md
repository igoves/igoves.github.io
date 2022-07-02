---
title: "tinykeys - маленькая (~ 400 B) библиотека для навешивания сочетаний клавиш на странице"
date: "2020-09-22"
categories: 
  - "js"
tags: 
  - "bind"
  - "key"
---

```
import tinykeys from "tinykeys"

tinykeys(window, {
  "Shift+D": () => {
    alert("The 'Shift' and 'd' keys were pressed at the same time")
  },
  "y e e t": () => {
    alert("The keys 'y', 'e', 'e', and 't' were pressed in order")
  },
  "$mod+KeyD": () => {
    alert("Either 'Control+d' or 'Meta+d' were pressed")
  },
})
```

[https://jamiebuilds.github.io/tinykeys/](https://jamiebuilds.github.io/tinykeys/)
