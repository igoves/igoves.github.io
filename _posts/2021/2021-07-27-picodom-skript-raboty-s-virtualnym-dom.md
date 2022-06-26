---
title: "picodom - скрипт работы с виртуальным DOM"
date: ""
categories: 
  - "js"
---

Пример

```
var { h, patch } = picodom
/** @jsx h */

let element, oldNode

function render(newNode) {
  return (element = patch(
    document.body,
    element,
    oldNode,
    (oldNode = newNode)
  ))
}

function view(state) {
  return (
    <div>
      <h1>{state}</h1>
      <input
        oninput={e => render(view(e.target.value))}
        value={state}
        type="text"
      />
    </div>
  )
}

render(view("Hello Picodom!"))
```

[https://github.com/picodom/picodom](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BpY29kb20vcGljb2RvbQ%3D%3D)
