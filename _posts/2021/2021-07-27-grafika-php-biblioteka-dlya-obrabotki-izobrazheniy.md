---
title: "grafika - php библиотека для обработки изображений"
categories: 
  - "php"
---

```
use Grafika\\Grafika;

$editor = Grafika::createEditor();

$editor->open( "path/to/jpeg/image.jpg" );
$editor->resizeExact( 200, 200 );
$editor->save( "path/to/edited.jpg", null, 90 );
```

  
Умеет обрезать, сравнивать, имеет фильтры и др.  
[http://kosinix.github.io/grafika/](https://dev.xfor.top/go/aHR0cDovL2tvc2luaXguZ2l0aHViLmlvL2dyYWZpa2Ev)
