---
title: "marcuswestin/store.js - js скрипт работы с локальным хранилищем"
date: ""
categories: 
  - "js"
---

```
// Store current user
store.set('user', { name:'Marcus' })

// Get current user
store.get('user')

// Remove current user
store.remove('user')

// Clear all keys
store.clearAll()

// Loop over all stored values
store.each(function(value, key) {
    console.log(key, '==', value)
})
```

  
[https://github.com/marcuswestin/store.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21hcmN1c3dlc3Rpbi9zdG9yZS5qcw%3D%3D)
