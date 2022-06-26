---
title: "Breakpoint.js - скрипт определяет ширину экрана и выполняет действие"
date: ""
categories: 
  - "js"
---

Пример использования  

```
import breakpoint from './modules/breakpoint.js';

let config = {
  // media query
  // type: string
  // required
  query: '(min-width: 1024px)',

  // callback to call when the query result is true
  // type: function
  // required
  success: () => console.log('Window width is above 1024px'),

  // function to call when the query result is false
  // type: function
  // optional
  fail: () => console.log('Window width is below 1024px')},

  // context to set on success and fail callbacks
  // type: object
  // default: null
  // optional
  context: window
};

// breakpoint will be automatically listening for changes
let destroyBreakpoint = breakpoint(config);

// if you need to stop listening for changes,
// just call the assigned variable
destroyBreakpoint();
```

  
[https://github.com/andrew--r/breakpoint/](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2FuZHJldy0tci9icmVha3BvaW50Lw%3D%3D)
