---
title: "html2text - скрипт для php, конверстирует html в text"
date: ""
categories: 
  - "php"
---

```
html>
<title>Ignored Title</title>
<body>
  <h1>Hello, World!</h1>

  <p>This is some e-mail content.
  Even though it has whitespace and newlines, the e-mail converter
  will handle it correctly.

  <p>Even mismatched tags.</p>

  <div>A div</div>
  <div>Another div</div>
  <div>A div<div>within a div</div></div>

  <a href="http://foo.com">A link</a>

</body>
</html>
```

  
На выходе получаем

```
Hello, World!

This is some e-mail content. Even though it has whitespace and newlines, the e-mail converter will handle it correctly.

Even mismatched tags.
A div
Another div
A div
within a div
[A link](http://foo.com)
```

  
[https://github.com/soundasleep/html2text](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NvdW5kYXNsZWVwL2h0bWwydGV4dA%3D%3D)
