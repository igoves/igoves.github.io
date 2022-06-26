---
title: "Rallax.js - js плагин для создания паралакс эффекта"
date: ""
categories: 
  - "js"
---

```
import rallax from 'rallax.js'

document.addEventListener('DOMContentLoaded', () => {
  window.onbeforeunload = () => {
    window.scrollTo(0, 0)
  }

  const dead = rallax('.dead', {speed: 0.55, mobilePx: 600})
  const simple = rallax('.simple', {speed: 0.7, mobilePx: 600})
  const parallax = rallax('.parallax', {speed: 0.6, mobilePx: 600})
  const scrolling = rallax('.scrolling', {speed: 0.75, mobilePx: 600})

  const objects = [dead, simple, parallax, scrolling]

  objects.forEach(obj => {
      obj.when(
        () => obj.scrollY() > 750,
        () => obj.stop()
      )
      obj.when(
        () => obj.scrollY() <= 750,
        () => obj.start()
      )
    })

  const image = document.querySelector('.parallax-image')
  const imageContainer = document.querySelector('.container')
  const imageContainerRect = imageContainer.getBoundingClientRect()
  const winHeight = window.innerHeight

  const imageTop = -(window.innerHeight * 0.3) * 2
  const imageHeight = imageContainerRect.height + (winHeight * 0.3)
  const imageWidth = imageContainerRect.width + 200
  const imageLeft = -100

  Object.assign(image.style, {
    position: 'relative',
    top: `${imageTop}px`,
    left: `${imageLeft}px`,
    height: `${imageHeight}px`,
    width: `${imageWidth}px`,
  })

  const imageParallax = rallax(image, {mobilePx: 600})
})
```

  
[https://chriscavs.github.io/rallax-demo/](https://dev.xfor.top/go/aHR0cHM6Ly9jaHJpc2NhdnMuZ2l0aHViLmlvL3JhbGxheC1kZW1vLw%3D%3D)
