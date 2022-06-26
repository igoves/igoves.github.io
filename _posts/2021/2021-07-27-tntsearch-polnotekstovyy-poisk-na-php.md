---
title: "TNTSearch - полнотекстовый поиск на PHP"
categories: 
  - "php"
---

Создание индекса  

```

    use TeamTNT\\TNTSearch\\TNTSearch;

    $tnt = new TNTSearch;

    $tnt->loadConfig([
        'driver'    => 'mysql',
        'host'      => 'localhost',
        'database'  => 'dbname',
        'username'  => 'user',
        'password'  => 'pass',
        'storage'   => '/var/www/tntsearch/examples/'
    ]);

    $indexer = $tnt->createIndex('name.index');
    $indexer->query('SELECT id, article FROM articles;');
    //$indexer->setLanguage('german');
    $indexer->run();
```

  
Поиск  

```
use TeamTNT\\TNTSearch\\TNTSearch;

    $tnt = new TNTSearch;

    $tnt->loadConfig($config);
    $tnt->selectIndex("name.index");

    $res = $tnt->search("This is a test search", 12);

    print_r($res); //returns an array of 12 document ids that best match your query

    //to display the results you need an additional query
    //SELECT * FROM articles WHERE id IN $res ORDER BY FIELD(id, $res);
```

  
[https://github.com/teamtnt/tntsearch](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3RlYW10bnQvdG50c2VhcmNo) | [DEMO](https://dev.xfor.top/go/aHR0cDovL3RudHNlYXJjaC50bnRzdHVkaW8udXMv)
