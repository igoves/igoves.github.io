---
title: "notti - js скрипт простого уведомления пользователя"
categories: 
  - "js"
---

![notti - js скрипт простого уведомления пользователя](https://camo.githubusercontent.com/22de571a329f7f71ee86281f63e35c9db8520834/68747470733a2f2f63646e2e7261776769742e636f6d2f6c75697376696e69636975733136372f6e6f7474692f6d61737465722f696d672f6e6f7474692e676966 "notti - js скрипт простого уведомления пользователя")

  
2.2 кб, без зависимостей, кастомизируется.  

```
import { notti } from 'notti';

notti('Hello User!');

notti({
  // HTML Element
  message: '<strong>Hello!</stong> User',
  isHTML: true,
  style : {
    backgroundColor: '#333',
    color:'#fff',
    bottom: '10px',
    right: '10px'
  },
  onHide: () => {
    console.log('Awesome notti.js!')
  }
});
```

  
[https://github.com/luisvinicius167/notti](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2x1aXN2aW5pY2l1czE2Ny9ub3R0aQ%3D%3D)
