---
title: "Лучший способ отложенной загрузки изображений для максимальной производительности"
date: "2020-10-14"
categories: 
  - "js"
tags: 
  - "images"
  - "lazy"
  - "load"
---

![](images/cqr1hz4w2vzas92rjvs7.png)

```
 <picture>
    <source data-srcset="path/to/image.webp" type="image/webp" />
    <source data-srcset="path/to/image.jpg" />
    <img loading="lazy" 
        class="lazyload"
        src="path/to/placeholder/image.png"
        data-src="path/to/image.jpg"
        alt="Image description"
    />
</picture>
```

```
<script>
    if ("loading" in HTMLImageElement.prototype) {
        var images = document.querySelectorAll('img[loading="lazy"]');
        var sources = document.querySelectorAll("source[data-srcset]");
        sources.forEach(function (source) {
            source.srcset = source.dataset.srcset;
        });
        images.forEach(function (img) {
            img.src = img.dataset.src;
        });
    } else {
        var script = document.createElement("script");
        script.src = "/link/to/lazyload.js";
        document.body.appendChild(script);
    }
</script>
```

[https://github.com/aFarkas/lazysizes](https://github.com/aFarkas/lazysizes)

Для нативной отложенной загрузки нам нужно только присвоить значение data-src значению src для img и исходных элементов и позволить браузеру обработать все остальное.

Для неподдерживаемых браузеров нам нужно только загрузить плагин JavaScript и, при желании, запустить его (если это не делается автоматически). Я использовал lazysize.
