---
title: "Fela - js скрипт для упралвения стилями"
categories: 
  - "js"
---

Пример использования

```
import { createRenderer, render } from 'fela'

// rules are just plain functions of props
// returning a valid object of style declarations
const rule = props => ({
  fontSize: props.fontSize + 'px',
  marginTop: props.margin ? '15px' : 0,
  color: 'red',
  lineHeight: 1.4,
  ':hover': {
    color: 'blue',
    fontSize: props.fontSize + 2 + 'px'
  },
  // nest media queries and pseudo classes
  // inside the style object
  '@media (min-height: 300px)': {
    backgroundColor: 'gray',
    ':hover': {
      color: 'black'
    }
  }
})

// Creates a new renderer to render styles
const renderer = createRenderer()

// Rendering the rule returns a className reference
// which can be attached to any element
const className = renderer.renderRule(rule, { fontSize: 12 }))

console.log(className) // => c0 c0-aw22w

// renders all styles into the DOM
render(renderer, mountNode)
```

  
[http://fela.js.org/](https://dev.xfor.top/go/aHR0cDovL2ZlbGEuanMub3JnLw%3D%3D)
