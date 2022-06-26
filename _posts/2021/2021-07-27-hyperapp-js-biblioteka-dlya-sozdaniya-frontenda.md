---
title: "hyperapp - js библиотека для создания фронтенда"
date: ""
categories: 
  - "js"
---

```
import { h, app } from "hyperapp"

const state = {
  count: 0
}

const actions = {
  down: () => state => ({ count: state.count - 1 }),
  up: () => state => ({ count: state.count + 1 })
}

const view = (state, actions) => (
  <main>
    <h1>{state.count}</h1>
    <button onclick={actions.down}>-</button>
    <button onclick={actions.up}>+</button>
  </main>
)

export const main = app(state, actions, view, document.body)
```

  
[https://github.com/hyperapp/hyperapp](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2h5cGVyYXBwL2h5cGVyYXBw)
