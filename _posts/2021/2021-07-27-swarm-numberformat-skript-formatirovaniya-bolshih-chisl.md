---
title: "swarm-numberformat - скрипт форматирования больших числ"
date: ""
categories: 
  - "js"
---

```
numberformat.format(1e10)    // or {format: 'standard'}
 // => "10.000 billion"
 numberformat.format(1e10, {format: 'scientific'})
 // => "1.0000e10"
 numberformat.format(1e10, {format: 'engineering'})
 // => "10.000E9"
 numberformat.format(1e10, {format: 'longScale'})
 // => "10.000 milliard"
```

  
[https://github.com/erosson/swarm-numberformat](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2Vyb3Nzb24vc3dhcm0tbnVtYmVyZm9ybWF0)
