---
title: "EasyGrid - создание гридов на vanilla JS"
date: "2020-12-08"
categories: 
  - "js"
tags: 
  - "grid"
---

![](images/easy_small.png)

```
document.addEventListener("DOMContentLoaded", function() {
     var demo1 = new EasyGrid({
       selector: "#grid",
       dimensions: {
         width: "150",
         height: "270",
         margin: "5",
         minHeight: "20", // if height is "random"
         maxHeight: "40"  // if height is "random"
       },
       animations: {
         fadeInSpeed: "100",
         addItemSpeed: "100"
       },
       style: {
         background: "transparent",
         borderRadius: "5"
       }
     });
     
     // Add items to Grid
     demo1.AddItem({
        items: "HTML Element"
     });
});
```

[https://github.com/BMSVieira/EasyGrid](https://github.com/BMSVieira/EasyGrid)
