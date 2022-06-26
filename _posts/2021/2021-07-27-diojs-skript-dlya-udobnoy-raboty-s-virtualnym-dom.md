---
title: "dio.js - скрипт для удобной работы с виртуальным DOM"
date: ""
categories: 
  - "js"
---

```
function HelloWorld () {
    return {
        render: function (props) {
            return h('h1', props.text);
            // or
            // return {type: 'h1', props: {}, children: [props.text]};
        }
    }
}

dio.createRender(HelloWorld)({text: 'Hello World'})
```

  
[https://github.com/thysultan/dio.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3RoeXN1bHRhbi9kaW8uanM%3D)
