---
title: "voku/anti-xss - protection against Cross-site scripting (XSS) via PHP"
date: "2021-07-30"
categories: 
  - "php"
tags: 
  - "anti"
  - "protection"
  - "xss"
---

```
$harm_string = '<li style="list-style-image: url(javascript:alert(0))">';
$antiXss->removeEvilAttributes(array('style')); // allow style-attributes
$harmless_string = $antiXss->xss_clean($harm_string);
```

[https://github.com/voku/anti-xss](https://github.com/voku/anti-xss)
