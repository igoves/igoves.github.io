---
title: "safe8 - all PHP functions, rewritten to throw exceptions instead of returning false, now for php8"
date: "2021-07-29"
categories: 
  - "php"
tags: 
  - "exceptions"
  - "throw"
---

```
use function Safe\file_get_contents;
use function Safe\json_decode;

// This code is both safe and simple!
$content = file_get_contents('foobar.json');
$foobar = json_decode($content);
```

[https://github.com/thecodingmachine/safe8](https://github.com/thecodingmachine/safe8)
