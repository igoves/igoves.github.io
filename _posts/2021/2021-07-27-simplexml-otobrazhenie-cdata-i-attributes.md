---
title: "SimpleXML отображение CDATA и attributes"
date: ""
categories: 
  - "php"
tags: 
  - "attributes"
  - "cdata"
  - "simplexml"
---

Что бы показывалась CDATA нужно использовать флажек LIBXML\_NOCDATA  

```
$feed = simplexml_load_file('http://site.ru/yml.xml', 'SimpleXMLElement', LIBXML_NOCDATA);
```

  
А что бы показывались еще и attributes нужно разбирать непосредственно необходимый параметр, смотреть пример  
**http://us.php.net/manual/en/function.simplexml-load-string.php#80855**
