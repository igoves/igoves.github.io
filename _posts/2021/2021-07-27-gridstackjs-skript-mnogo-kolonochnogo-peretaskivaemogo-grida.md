---
title: "gridstack.js - скрипт много колоночного перетаскиваемого грида"
categories: 
  - "js"
---

![gridstack.js - скрипт много колоночного перетаскиваемого грида](images/1450089418_untitled-2.png "gridstack.js - скрипт много колоночного перетаскиваемого грида")

  
Пример использования

```
<div class="grid-stack">
    <div class="grid-stack-item" 
        data-gs-x="0" data-gs-y="0" 
        data-gs-width="4" data-gs-height="2">
            <div class="grid-stack-item-content"></div>
    </div>
    <div class="grid-stack-item" 
        data-gs-x="4" data-gs-y="0" 
        data-gs-width="4" data-gs-height="4">
            <div class="grid-stack-item-content"></div>
    </div>
</div>

<script type="text/javascript">
$(function () {
    var options = {
        cell_height: 80,
        vertical_margin: 10
    };
    $('.grid-stack').gridstack(options);
});
</script>
```

  
[http://troolee.github.io/gridstack.js/](https://dev.xfor.top/go/aHR0cDovL3Ryb29sZWUuZ2l0aHViLmlvL2dyaWRzdGFjay5qcy8%3D)
