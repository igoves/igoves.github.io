---
title: "vstelmakh / url-highlight - библиотека для анализа URL-адресов из строкового ввода"
date: "2020-06-27"
categories: 
  - "php"
tags: 
  - "highlight"
  - "url"
---

```
<?php
require __DIR__ . '/vendor/autoload.php';

use VStelmakh\UrlHighlight\UrlHighlight;

$urlHighlight = new UrlHighlight();
echo $urlHighlight->highlightUrls('Hello, http://example.com.');

// Output:
// Hello, <a href="http://example.com">http://example.com</a>.
```

[https://github.com/vstelmakh/url-highlight](https://github.com/vstelmakh/url-highlight)
