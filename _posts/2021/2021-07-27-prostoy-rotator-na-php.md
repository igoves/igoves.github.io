---
title: "Простой ротатор на PHP"
categories: 
  - "php"
---

```
<?php$banner1 = '<a href="BANNER1_URL" target="_blank"><img src="BANNER1_IMG_SRC" alt="BANNER1_ALT" title="BANNER1_TITLE"></a>';$banner2 = '<a href="BANNER2_URL" target="_blank"><img src="BANNER2_IMG_SRC" alt="BANNER2_ALT" title="BANNER2_TITLE"></a>';$banner3 = '<a href="BANNER3_URL" target="_blank"><img src="BANNER3_IMG_SRC" alt="BANNER3_ALT" title="BANNER3_TITLE"></a>';$banner4 = '<a href="BANNER4_URL" target="_blank"><img src="BANNER4_IMG_SRC" alt="BANNER4_ALT" title="BANNER4_TITLE"></a>';$banners = array($banner1, $banner2, $banner3, $banner4);shuffle($banners);?>
```
