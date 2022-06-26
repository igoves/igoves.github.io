---
title: "logerr - js скрипт для отладки"
date: ""
categories: 
  - "js"
---

Вместо

```
var test = a + 1; //a is not defined
```

  
Будет

```
Type: error
Error: Uncaught ReferenceError: a is not defined
StackTrace: ReferenceError: a is not defined at http://localhost:8888/logerr/logerr.min.js:3:12
File Name: logerr.js
Path: http://localhost:8888/logerr/logerr.js
Line: 51
Column: 12
Date: Tue Jun 28 2016 19:51:22 GMT+0530 (IST)
Debug: http://localhost:8888/logerr/logerr.js:51
Get Help: https://stackoverflow.com/search?q=Uncaught+ReferenceError:+a+is+not+defined
```

  
[https://i-break-codes.github.io/logerr/](https://dev.xfor.top/go/aHR0cHM6Ly9pLWJyZWFrLWNvZGVzLmdpdGh1Yi5pby9sb2dlcnIv)
