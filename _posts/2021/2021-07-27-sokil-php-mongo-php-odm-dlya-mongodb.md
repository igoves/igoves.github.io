---
title: "sokil/php-mongo - php ODM для mongodb"
categories: 
  - "php"
---

Пример получения данных

```
<?php
$document->requiredField; // defaultValue
$document->get('requiredField'); // defaultValue
$document->getRequiredField(); // defaultValue

$document->someField; // ['subDocumentField' => 'value']
$document->get('someField'); // ['subDocumentField' => 'value']
$document->getSomeField(); // ['subDocumentField' => 'value']
$document->get('someField.subDocumentField'); // 'value'

$document->get('some.unexisted.subDocumentField'); // null
```

  
[https://github.com/sokil/php-mongo](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Nva2lsL3BocC1tb25nbw%3D%3D)
