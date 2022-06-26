---
title: "RedBeanPHP - php ORM для работы с базами данных"
categories: 
  - "php"
---

Поддерживает через pdo драйвер такие бд: MySQL, MariaDB, SQLite, PostgreSQL and CUBRID  

```
    require 'rb.php';
    R::setup();
    R::setAutoResolve( TRUE );        //Recommended as of version 4.2
    $post = R::dispense( 'post' );
    $post->text = 'Hello World';

    $id = R::store( $post );          //Create or Update
    $post = R::load( 'post', $id );   //Retrieve
    R::trash( $post );                //Delete
```

  
[http://redbeanphp.com/](https://dev.xfor.top/go/aHR0cDovL3JlZGJlYW5waHAuY29tLw%3D%3D)
