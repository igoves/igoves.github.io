---
title: "laravolt/avatar - плагин создания аватара на основе имени для laravel"
categories: 
  - "php"
---

![laravolt/avatar - плагин создания аватара на основе имени для laravel](images/6dbd77e2-47ea-11e7-8a05-7772465309c5.png "laravolt/avatar - плагин создания аватара на основе имени для laravel")

  

```
//this will output data-uri (base64 image data)
//something like data:image/png;base64,iVBORw0KGg....
Avatar::create('Joko Widodo')->toBase64();

//use in view
//this will display initials JW as an image
<img src="{{ Avatar::create('Joko Widodo')->toBase64() }}" />
```

  
[https://github.com/laravolt/avatar](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2xhcmF2b2x0L2F2YXRhcg%3D%3D)
