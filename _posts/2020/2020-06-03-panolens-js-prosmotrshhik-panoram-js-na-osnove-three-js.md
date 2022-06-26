---
title: "panolens.js - просмотрщик панорам js на основе Three.js"
date: "2020-06-03"
categories: 
  - "js"
tags: 
  - "panorama"
  - "threejs"
  - "viewer"
---

![](https://github.com/pchen66/pchen66.github.io/raw/master/Panolens/images/panolens.gif?raw=true)

Panolens.js - это программа для просмотра панорам на основе событий и WebGL. Легкий и гибкий. Он построен поверх Three.JS.

```
const panorama = new PANOLENS.ImagePanorama( 'asset/equirectangular.jpg' );
const viewer = new PANOLENS.Viewer();
viewer.add( panorama );
```

[https://github.com/pchen66/panolens.js](https://github.com/pchen66/panolens.js)
