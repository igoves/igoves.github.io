---
title: "Черновик по основным запросам Mongodb через PHP"
date: ""
categories: 
  - "php"
tags: 
  - "mongo"
  - "nosql"
  - "php"
---

Инициализация

```
try {
	$mongo = new MongoClient("mongodb://localhost:27017/yourtable");
	$db= $mongo->selectDB("yourtable");
        $collection = $db->yourcollection;
} catch (MongoConnectionException $e) {
	die('Error connecting to MongoDB server. ' . $e->getMessage());
} catch (MongoException $e) {
	die('Error: ' . $e->getMessage());
}
```

  
[http://www.querymongo.com/](https://dev.xfor.top/go/aHR0cDovL3d3dy5xdWVyeW1vbmdvLmNvbS8%3D) - онлайн сервис преобразует sql select в mongo select (если запрос чуть сложнее обычного сразу использует reduce, я же предпочитаю использовать aggregate)  
  

```
<?php

// INSERT
$data_insert = array(
	// data insert
);		
$collection->insert($data_insert);
// lastID:  (string)$data_insert['_id'];


// SELECT
$query = array(
	// where
);
$projection = array(
	// return
);
$cursor = $collection->find($query, $projection)
					->skip($start)
					->limit($limit)
					->sort(array('field'=> -1));
foreach ($cursor as $row) {
	echo "<pre>";
	print_r($row);
	echo "</pre>";	
}
// count
$count = $collection->count();


// SELECT_ONE
$query = array(
	// where
);
$projection = array(
	// return
);
$row = $collection->findOne($query, $projection);
echo "<pre>";
print_r($row);
echo "</pre>";	


// UPDATE
$criteria = array(
	// where
);
$update = array(
	// set
);
$options = array(
	// upsert: true, multi: true
);
$collection->update($criteria, $update, $options);


// DELETE
$query = array(
	// where
);
$options = array (
	'justOne' => true
);
$cursor = $collection->remove($query, $options);	


// COMPLEX SELECT
$data = $collection->aggregate( 
	array(
		'$match' => array(
			// where
		) 
	),
	array(
		'$project' => array(
			// manipulate fields
		)
	),
	array(
		'$group' => array(
			// group
		)
	),
	array(
		'$skip' => array(
			// skip
		)
	),
	array(
		'$limit' => array(
			// limit
		)
	),	
	array(
		'$sort' => array(
			// sort
		)
	)
); 
// print_r($data);
```
