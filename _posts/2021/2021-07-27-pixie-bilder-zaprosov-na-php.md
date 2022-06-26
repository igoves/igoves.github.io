---
title: "pixie - билдер запросов на php"
date: ""
categories: 
  - "php"
---

```
// Make sure you have Composer's autoload file included
require 'vendor/autoload.php';

// Create a connection, once only.
$config = array(
            'driver'    => 'mysql', // Db driver
            'host'      => 'localhost',
            'database'  => 'your-database',
            'username'  => 'root',
            'password'  => 'your-password',
            'charset'   => 'utf8', // Optional
            'collation' => 'utf8_unicode_ci', // Optional
            'prefix'    => 'cb_', // Table prefix, optional
            'options'   => array( // PDO constructor options, optional
                PDO::ATTR_TIMEOUT => 5,
                PDO::ATTR_EMULATE_PREPARES => false,
            ),
        );

new \\Pixie\\Connection('mysql', $config, 'QB');
```

Пример запроса

```
$row = QB::table('my_table')->find(3);
```

  
[https://github.com/usmanhalalit/pixie](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3VzbWFuaGFsYWxpdC9waXhpZQ%3D%3D)
