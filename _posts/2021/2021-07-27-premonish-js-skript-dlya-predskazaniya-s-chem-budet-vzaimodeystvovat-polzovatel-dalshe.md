---
title: "premonish - js скрипт для предсказания, с чем будет взаимодействовать пользователь дальше"
date: ""
categories: 
  - "js"
---

Пример

```
import Premonish from 'premonish';
const premonish = new Premonish({
  selectors: ['a', '.list-of' '.selectors', '.to', '#watch'],
  elements: [] // Alternatively, provide a list of DOM elements to watch
});

premonish.onIntent(({el, confidence}) => {
  console.log(el); // The DOM node we suspect the user is about to interact with.
  console.log(confidence); // How confident are we about the user's intention? Scale 0-1
});
```

  
[https://mathisonian.github.io/premonish/](https://dev.xfor.top/go/aHR0cHM6Ly9tYXRoaXNvbmlhbi5naXRodWIuaW8vcHJlbW9uaXNoLw%3D%3D)
