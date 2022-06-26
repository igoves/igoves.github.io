---
title: "fontmin - npm плагин для минимизации шрифтов"
date: ""
categories: 
  - "js"
---

```
var Fontmin = require('fontmin');var fontmin = new Fontmin()    .src('fonts/*.ttf')    .dest('build/fonts');fontmin.run(function (err, files) {    if (err) {        throw err;    }    console.log(files[0]);    // => { contents: <Buffer 00 01 00 ...> }});
```

  
[https://github.com/ecomfe/fontmin](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2Vjb21mZS9mb250bWlu)
