---
title: "MongoQB - php обертка для запросов в mongo"
categories: 
  - "php"
---

Подключение

```
$qb = \\MongoQB\\Builder(array(
    'dsn'   =>  'mongodb://user:pass@localhost:27017/databaseName'
);
```

Вставка

```
$qb->insert('collectionName', [
    'name'  =>  'Alex',
    'age'   =>  22,
    'likes' =>  ['whisky', 'gin']
]);
```

Обновление

```
$qb
    ->where(['name' => 'Alex'])
    ->set([
        'country' => 'UK',
        'job' => 'Developer'
    ])
    ->push('likes', ['PHP', 'coffee'])
    ->update('collectionName');
```

  
[https://github.com/alexbilbie/MongoQB](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2FsZXhiaWxiaWUvTW9uZ29RQg%3D%3D)
