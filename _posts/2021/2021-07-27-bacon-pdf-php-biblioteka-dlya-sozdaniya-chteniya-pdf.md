---
title: "Bacon PDF - php библиотека для создания - чтения pdf"
date: ""
categories: 
  - "php"
---

Пример создания пустой страницы

```
use Bacon\\Pdf\\PdfWriter;
require_once __DIR__ . '/../vendor/autoload.php';
$writer = PdfWriter::toFile(__DIR__ . '/empty-page.pdf');
$writer->getDocumentInformation()->set('Title', 'Empty Page Example');
$writer->addPage(595, 842);
$writer->endDocument();
```

  
[https://github.com/Bacon/BaconPdf](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0JhY29uL0JhY29uUGRm)
