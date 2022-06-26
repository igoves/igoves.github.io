---
title: "PDF Parser - php библиотека для парсинга pdf файлов"
date: ""
categories: 
  - "php"
---

```
<?php

// Include Composer autoloader if not already done.
include 'vendor/autoload.php';

// Parse pdf file and build necessary objects.
$parser = new \\Smalot\\PdfParser\\Parser();
$pdf    = $parser->parseFile('document.pdf');

$text = $pdf->getText();
echo $text;
```

  
[http://www.pdfparser.org](https://dev.xfor.top/go/aHR0cDovL3d3dy5wZGZwYXJzZXIub3Jn)
