---
title: "callmecavs/gotem - js скрипт копирования в буфер на современных браузерах"
date: ""
categories: 
  - "js"
---

```
import gotem from 'gotem'

// a trigger and target node are required
const nodes = {
  trigger: document.getElementById('trigger'),
  target: document.getElementById('target')
}

// when the trigger is clicked,
// the text of the target will be copied to the clipboard
gotem(nodes.trigger, nodes.target)

// if an object with callback functions (success, error) is passed,
// the appropriate function, based on the result of executing the copy command, will be fired if it exists
gotem(nodes.trigger, nodes.target, {
  success: () => console.log('Copy command succeeded'),
  error: () => console.log('Copy command failed, BUT the text to copy has still been selected.')
})
```

  
[https://github.com/callmecavs/gotem](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2NhbGxtZWNhdnMvZ290ZW0%3D)
