---
title: "latitude - php конструктор запросов SQL"
categories: 
  - "php"
---

Пример SELECT

```
use Latitude\\QueryBuilder\\SelectQuery;

$select = SelectQuery::make()
    ->from('users');

echo $select->sql();
// SELECT * FROM users
```

  
[https://github.com/shadowhand/latitude](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NoYWRvd2hhbmQvbGF0aXR1ZGU%3D)
