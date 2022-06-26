---
title: "Ошибка Call to undefined function json_decode() или json_encode()"
date: ""
categories: 
  - "php"
---

Это значит, что у Вас не определяется функция json\_decode() или json\_encode(). А это может быть в случае если у вас php ниже 5.2.0. 
  
Как это пофиксить без обновления:  
  
Качаем либу [http://mike.teczno.com/JSON.tar.gz](https://dev.xfor.top/go/aHR0cDovL21pa2UudGVjem5vLmNvbS9KU09OLnRhci5neg%3D%3D)  
  
Вставляем где нужно:  

```
if( !function_exists('json_encode') ) {    function json_encode($data) {        $json = new Services_JSON();        return( $json->encode($data) );    }}// Future-friendly json_decodeif( !function_exists('json_decode') ) {    function json_decode($data, $bool) {        if ($bool) {            $json = new Services_JSON(SERVICES_JSON_LOOSE_TYPE);        } else {            $json = new Services_JSON();        }        return( $json->decode($data) );    }}
```

  
  
Подключаем либу:  

```
include("JSON.php");
```

  
  
Всо -) пс, ТыЦ Дэсять -)
