---
title: "js-url - простой, легкий парсер url на js"
categories: 
  - "js"
tags: 
  - "js"
  - "parse"
  - "url"
  - "url-js"
---

http://rob:abcd1234@www.example.com/path/index.html?query1=test&silly=willy#test=hash&chucky=cheese

```
url();            // http://rob:abcd1234@www.example.com/path/index.html?query1=test&silly=willy#test=hash&chucky=cheeseurl('domain');    // example.comurl('hostname');  // www.example.comurl('tld');       // comurl('sub');       // wwwurl('.0')         // (an empty string)url('.1')         // wwwurl('.2')         // exampleurl('.-1')        // comurl('auth')       // rob:abcd1234url('user')       // roburl('pass')       // abcd1234url('port');      // 80url('protocol');  // httpurl('path');      // /path/index.htmlurl('file');      // index.htmlurl('filename');  // indexurl('fileext');   // htmlurl('1');         // pathurl('2');         // index.htmlurl('3');         // (an empty string)url('-1');        // index.htmlurl(1);           // pathurl(2);           // index.htmlurl(-1);          // index.htmlurl('?');         // query1=test&silly=willyurl('?silly');    // willyurl('?poo');      // (an empty string)url('#');         // test=hash&chucky=cheeseurl('#chucky');   // cheeseurl('#poo');      // (an empty string)
```

  
[https://github.com/websanova/js-url](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dlYnNhbm92YS9qcy11cmw%3D)
