---
title: "PHPWord - php библиотека для чтения и записи word документов"
categories: 
  - "php"
---

На текущий момент поддерживает Microsoft Office Open XML (OOXML or OpenXML), OASIS Open Document Format for Office Applications (OpenDocument or ODF), Rich Text Format (RTF), HTML, and PDF.  

```
<?php
require_once 'src/PhpWord/Autoloader.php';
\\PhpOffice\\PhpWord\\Autoloader::register();

// Creating the new document...
$phpWord = new \\PhpOffice\\PhpWord\\PhpWord();

/* Note: any element you append to a document must reside inside of a Section. */

// Adding an empty Section to the document...
$section = $phpWord->addSection();

// Adding Text element with font customized inline...
$section->addText(
    htmlspecialchars(
        '"Great achievement is usually born of great sacrifice, '
            . 'and is never the result of selfishness." '
            . '(Napoleon Hill)'
    ),
    array('name' => 'Tahoma', 'size' => 10)
);
```

  
[https://github.com/PHPOffice/PHPWord](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1BIUE9mZmljZS9QSFBXb3Jk)
