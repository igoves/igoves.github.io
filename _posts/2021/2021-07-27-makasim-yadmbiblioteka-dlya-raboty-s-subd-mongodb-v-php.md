---
title: "makasim/yadm — библиотека для работы с СУБД MongoDB в PHP"
date: ""
categories: 
  - "php"
---

```
$order = new Order();
set_value($order, 'id', Uuid::generate()->toString());
set_value($order, 'createdAt', (new \\DateTime())->format('U'));

$storage->insert($order);

$id = get_value($order, 'id');

// find by uuid
$anotherOrder = $storage->findOne(['id' => new Uuid($id)]);

// do not update id if not changed
$storage->update($anotherOrder);

// update on change
set_value($anotherOrder, 'id', Uuid::generate()->toString());
$storage->update($anotherOrder);
```

  
[https://github.com/makasim/yadm](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21ha2FzaW0veWFkbQ%3D%3D)
