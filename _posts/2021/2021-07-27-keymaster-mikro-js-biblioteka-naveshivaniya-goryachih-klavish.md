---
title: "keymaster - микро js библиотека навешивания горячих клавиш"
categories: 
  - "js"
---

```
// define short of 'a'
key('a', function(){ alert('you pressed a!') });

// returning false stops the event and prevents default browser events
key('ctrl+r', function(){ alert('stopped reload!'); return false });

// multiple shortcuts that do the same thing
key('?+r, ctrl+r', function(){ });
```

  
[https://github.com/madrobby/keymaster](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21hZHJvYmJ5L2tleW1hc3Rlcg%3D%3D)
