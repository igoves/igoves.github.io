---
title: "gulp-selectors - плагин для gulp сокращает имена классов и id"
categories: 
  - "note"
---

```
var processors = {
        'css':  ['scss', 'css'],        // run the css processor on .scss and .css files 
        'html': ['haml'],               // run the html processor on .haml files 
        'js-strings':   ['js']          // run the js-strings plugin on js files 
    },
    ignores = {
        classes: ['hidden', 'active']   // ignore these class selectors, 
        ids: '*'                        // ignore all IDs 
    };
 
gs.run(processors, ignores);
```

  
[https://www.npmjs.com/package/gulp-selectors](https://dev.xfor.top/go/aHR0cHM6Ly93d3cubnBtanMuY29tL3BhY2thZ2UvZ3VscC1zZWxlY3RvcnM%3D) и не забываем про [Обзор полезных gulp плагинов](/1784-obzor-poleznyh-gulp-plaginov.html)
