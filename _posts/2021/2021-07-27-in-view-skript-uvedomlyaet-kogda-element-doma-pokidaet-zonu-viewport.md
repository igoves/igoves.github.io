---
title: "in-view - скрипт уведомляет когда элемент дома покидает зону viewport"
date: ""
categories: 
  - "js"
---

[![in-view - скрипт уведомляет когда элемент дома покидает зону viewport](https://camo.githubusercontent.com/d27edeef02aee93ee7c51d99f4d3251c25dbace1/68747470733a2f2f63616d776965676572742e6769746875622e696f2f696e2d766965772f6c69622f696d616765732f696e2d766965772e706e67 "in-view - скрипт уведомляет когда элемент дома покидает зону viewport")](https://camo.githubusercontent.com/d27edeef02aee93ee7c51d99f4d3251c25dbace1/68747470733a2f2f63616d776965676572742e6769746875622e696f2f696e2d766965772f6c69622f696d616765732f696e2d766965772e706e67)

  

```
inView('.someSelector')
    .on('enter', doSomething)
    .on('exit', el => {
        el.style.opacity = 0.5;
    });
```

  
[https://github.com/camwiegert/in-view](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2NhbXdpZWdlcnQvaW4tdmlldw%3D%3D)
