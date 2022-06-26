---
title: "Granim.js - скрипт создания градиентной анимации"
categories: 
  - "js"
---

![Granim.js - скрипт создания градиентной анимации](images/1473664702_untitled-3.jpg "Granim.js - скрипт создания градиентной анимации")

  

```
<!-- Create a <canvas> element -->
<canvas id="granim-canvas"></canvas>

<!-- Call the script -->
<script src="granim.min.js"></script>

<!-- Create a Granim instance -->
<script>
var granimInstance = new Granim({
   element: '#granim-canvas',
   name: 'granim',
   opacity: [1, 1],
   states : {
       "default-state": {
           gradients: [
               ['#834D9B', '#D04ED6'],
               ['#1CD8D2', '#93EDC7']
           ]
       }
   }
});
</script>
```

  
[https://github.com/sarcadass/granim.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NhcmNhZGFzcy9ncmFuaW0uanM%3D)
