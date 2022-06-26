---
title: "easydb - простая обертка для PDO"
date: ""
categories: 
  - "php"
---

PDO

```
$db = new \\PDO(
    'mysql:host=localhost;dbname=something',
    'username',
    'putastrongpasswordhere'
);

$statement = $db->prepare('SELECT * FROM comments WHERE blogpostid = ? ORDER BY created ASC');
$exec = $statement->execute([$_GET['blogpostid']]);
$rows = $exec->fetchAll(\\PDO::FETCH_ASSOC);
foreach ($rows as $row) {
    $template_engine->render('comment', $row);
}
```

  
EasyDB

```
$db = \\ParagonIE\\EasyDB\\Factory::create(
    'mysql:host=localhost;dbname=something',
    'username',
    'putastrongpasswordhere'
);

$rows = $db->run('SELECT * FROM comments WHERE blogpostid = ? ORDER BY created ASC', $_GET['blogpostid']);
foreach ($rows as $row) {
    $template_engine->render('comment', $row);
}
```

  
[https://github.com/paragonie/easydb](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BhcmFnb25pZS9lYXN5ZGI%3D)
