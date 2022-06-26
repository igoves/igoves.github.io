---
title: "sabre-xml - специализированный XML reader and writer"
date: ""
categories: 
  - "php"
---

Если вы попробовали поработать [SimpleXML](https://dev.xfor.top/go/aHR0cDovL3BocC5uZXQvbWFudWFsL2VuL2Jvb2suc2ltcGxleG1sLnBocA%3D%3D) и с [the DOM](https://dev.xfor.top/go/aHR0cDovL2NhMi5waHAubmV0L21hbnVhbC9lbi9ib29rLmRvbS5waHA%3D) и все равно не устроило, то **sabre-xml** для вас.  
  
Пример создания XML

```
$xmlWriter = new Sabre\\Xml\\Writer();
$xmlWriter->openMemory();
$xmlWriter->startDocument();
$xmlWriter->setIndent(true);
$xmlWriter->namespaceMap = ['http://example.org' => 'b'];

$xmlWriter->write(['{http://example.org}book' => [
    '{http://example.org}title' => 'Cryptonomicon',
    '{http://example.org}author' => 'Neil Stephenson',
]]);
```

Получаем

```
<?xml version="1.0"?>
<b:book xmlns:b="http://example.org">
 <b:title>Cryptonomicon</b:title>
 <b:author>Neil Stephenson</b:author>
</b:book>
```

  
[http://sabre.io/xml/](https://dev.xfor.top/go/aHR0cDovL3NhYnJlLmlvL3htbC8%3D)
