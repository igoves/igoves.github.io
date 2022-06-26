---
title: "kpdecker/jsdiff - реализация различий в тексте JavaScript"
categories: 
  - "js"
---

```
require('colors');
var Diff = require('diff');

var one = 'beep boop';
var other = 'beep boob blah';

var diff = Diff.diffChars(one, other);

diff.forEach(function(part){
  // green for additions, red for deletions
  // grey for common parts
  var color = part.added ? 'green' :
    part.removed ? 'red' : 'grey';
  process.stderr.write(part.value[color]);
});

console.log();
```

  

![kpdecker/jsdiff - реализация различий в тексте JavaScript](images/node_example.png "kpdecker/jsdiff - реализация различий в тексте JavaScript")

  
[https://github.com/kpdecker/jsdiff](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2twZGVja2VyL2pzZGlmZg%3D%3D)
