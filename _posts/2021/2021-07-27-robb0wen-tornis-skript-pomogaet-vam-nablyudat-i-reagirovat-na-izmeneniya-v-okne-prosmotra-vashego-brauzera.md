---
title: "robb0wen/tornis -  скрипт помогает вам наблюдать и реагировать на изменения в окне просмотра вашего браузера"
date: ""
categories: 
  - "js"
---

![robb0wen/tornis - скрипт помогает вам наблюдать и реагировать на изменения в окне просмотра вашего браузера](images/1560932750_bezymyannyy.jpg "robb0wen/tornis - скрипт помогает вам наблюдать и реагировать на изменения в окне просмотра вашего браузера")

  

```
// import the Tornis store functions
import { 
  watchViewport, 
  unwatchViewport, 
  getViewportState
} from 'tornis';

// define a watched function, to be run on each update
const updateValues = ({ size, scroll, mouse, orientation }) => {
  if (size.changed) {
    // do something related to size
  }
  
  if (scroll.changed) {
    // do something related to scroll position or velocity
  }

  if (mouse.changed) {
    // do something related to mouse position or velocity
  }
};

// bind the watch function
// By default this will run the function as it is added to the watch list
watchViewport(updateValues);

// to bind the watch function without calling it
watchViewport(updateValues, false);

// when you want to stop updating
unwatchViewport(updateValues);

// to get a snapshot of the current viewport state
const state = getViewportState();
```

  
[https://github.com/robb0wen/tornis](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3JvYmIwd2VuL3Rvcm5pcw%3D%3D)
