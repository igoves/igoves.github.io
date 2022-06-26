---
title: "tung - js библиотека для построения html"
categories: 
  - "js"
---

```
<!-- page.tpl -->
<div>
    <div class="users">
        <Card block="users" />
    </div>
    <Btn block="btn" />
</div>

<!-- btn.tpl -->
<span class="btn">{this.text}</span>

<!-- card.tpl -->
<div class="item item--admin">
    <img src={this.img} width="50" height="50" />
    <span class="item__content">{this.name}<span block="isAdmin"> &bull; admin</span></span>
    <Btn block="btn"/>
    <Btn block="delete"/>
</div>
```

  
[https://github.com/Reon90/tung](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1Jlb245MC90dW5n)
