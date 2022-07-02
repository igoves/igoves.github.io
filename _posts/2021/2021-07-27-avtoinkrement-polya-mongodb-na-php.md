---
title: "Автоинкремент поля Mongodb на PHP"
categories: 
  - "note"
tags: 
  - "autoincrement"
  - "mongodb"
---

**Способ 1** когда документы коллекции только добавляются и не удаляются:  
Перед вставкой считаем количество документов и добавляем единицу  

```
$data_insert['num'] = $collection->count()+1;
$collection->insert($data_insert);
```

То есть всегда получаем количество документов +1. Если в таком случае удалить запись то счетчик собьется и нумерация нарушится. Поэтому используйте в том случаее когда документы не удаляются.  
  
**Способ 2** когда документы коллекции удаляются:  
Создается отдельная коллекция со счетчиками и вот таким документом к примеру  

```
$data_insert = array(
	'field' => 'user_id',
	'nextId' => 0
);
$collection = $db->selectCollection('counters');
$collection->insert($data_insert);
```

  
После чего добавление новых документов выглядит таким образом  

```
$collection = $db->selectCollection('counters');
$retval = $collection->findAndModify(
	array('field' => 'user_id'),
	array('$inc' => array("nextId" => 1)),
	null,
	array(
		"new" => true,
	)
);
$num = $retval['nextId'];
```

Здесь мы добавили 1 для нашего счетчика, теперь добавляется сам документ  

```
$collection = $db->selectCollection('users');
$data_insert['num'] = $num;
$collection->insert($data_insert);
```

  
Создасться запись с полем num = 1, следующая num = 2 и тд.  
  
Теперь когда удалится документ, счетчик не собьется, а продолжит работать и добавлять 1 при добавлении.
