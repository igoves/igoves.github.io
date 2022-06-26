---
title: "muicss/loadjs - простой маленький загрузчик"
date: ""
categories: 
  - "js"
---

```
// define a dependency bundle
loadjs(['/path/to/foo.js', '/path/to/bar.js'], 'foobar');

// execute code elsewhere when the bundle has loaded
loadjs.ready('foobar', {
  success: function() { /* foo.js & bar.js loaded */ },
  error: function(depsNotFound) { /* foobar bundle load failed */ }
});
```

  
[https://github.com/muicss/loadjs](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL211aWNzcy9sb2FkanM%3D)
