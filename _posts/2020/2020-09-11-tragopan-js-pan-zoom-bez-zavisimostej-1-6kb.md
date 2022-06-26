---
title: "tragopan - js pan/zoom без зависимостей (1.6kb)"
date: "2020-09-11"
categories: 
  - "js"
tags: 
  - "pan"
  - "zoon"
---

```
 <div id="viewport">
    <div id="content">
      <!-- your pan/zoomable content here -->
    </div>
  </div>

  <script>
    const tragopan = new Tragopan({
      viewport: document.querySelector('#viewport'),
      content: document.querySelector('#content')
    });
  </script>
```

[https://github.com/team-video/tragopan](https://github.com/team-video/tragopan)
