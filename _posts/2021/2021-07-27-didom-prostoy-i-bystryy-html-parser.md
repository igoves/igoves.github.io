---
title: "DiDOM - простой и быстрый html парсер"
date: ""
categories: 
  - "php"
---

```
use DiDom\\Document;

$document = new Document('http://www.news.com/', true);

$posts = $document->find('.post');

foreach($posts as $post) {
    echo $post->text(), "\\n";
}
```

  
[https://github.com/imangazaliev/didom](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2ltYW5nYXphbGlldi9kaWRvbQ%3D%3D)
