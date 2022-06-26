---
title: "Новый драйвер mongodb для PHP - черновик по основным запросам"
date: ""
categories: 
  - "note"
tags: 
  - "driver"
  - "mongodb"
---

Ранее писал [черновик по основным запросам](https://dev.xfor.top/1856-chernovik-po-osnovnym-zaprosam-mongodb-cherez-php.html) Mongodb в PHP, но стоило обновить пхп, и каково было мое разочарование, новый драйвер php для mongo полностью поменял синтаксис.  
Это хорошо, что не стоит на месте, и плохо, что придется переписывать. На данный момент (написания статьи, а не ее публикации) нет ни одной odm и orm поддерживающей новый драйвер. Только библиотека которая является оберткой для драйвера, и какой-то не полной (http://mongodb.github.io/mongo-php-library/api/index.html)  
  
Вот наш герой: https://github.com/mongodb/mongo-php-driver  
**pecl/mongodb** это новый MongoDB driver для PHP, а раньше это был его наследник pecl/mongo driver.  
  
Что же делать и как дальше быть, попытаемся разобраться.  
Документация http://php.net/manual/ru/set.mongodb.php  
Поехали:  

```
<?php
// INIT
$mongo = new MongoDB\\Driver\\Manager("mongodb://localhost:27017");


// INSERT
$document = ["hello" => "world"];
$bulk = new MongoDB\\Driver\\BulkWrite;
$id = $bulk->insert($document);
try {
    $result = $mongo->executeBulkWrite('mydb.collection', $bulk);
    echo (string)$id;
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}


// SELECT
$filter = [
    'hello' => 'world'
];
$options = [
    'projection' => [
        'hello' => 1,
    ],
    'sort' => [
        "hello" => -1,
    ],
    'skip' => 2,
    'limit' => 5
];
$query = new MongoDB\\Driver\\Query($filter, $options);
try {
    $cursor = $mongo->executeQuery('mydb.collection', $query);
    // здесь тоже можно посчитать количество с помощью iterator_count($cursor)
    // если хотите работать как с массивом а не обьектом, то приходится преобразовывать =(
    $cursor = MongoDB\\BSON\\fromPHP($cursor->toArray());
    $cursor = json_decode(MongoDB\\BSON\\toJSON($cursor), true);
    //
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}
foreach($cursor as $document) {
    echo "<pre>";
    print_r($document);
    echo "</pre>";
}
// count считаем так или смотрите ниже выполнение count c помощью Command
$count = count($cursor); */


// SELECT_ONE
// аналогично // SELECT только limit указуем в 1


// UPDATE
$filter = ["hello" => "world"];
$update = ['$set' => ["hello" => "wonderful world"]];
$options = ["limit" => 1, "upsert" => false];
$bulk = new MongoDB\\Driver\\BulkWrite;
$bulk->update($filter, $update, $options);
try {
    $result = $mongo->executeBulkWrite('mydb.collection', $bulk);
    var_dump($result);
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}


// DELETE
$filter = ['hello' => 'world'];
$options = ["limit" => 1];
$bulk = new MongoDB\\Driver\\BulkWrite;
$bulk->delete($filter, $options);
try {
    $result = $mongo->executeBulkWrite('mydb.collection', $bulk);
    var_dump($result);
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}


// ВЫПОЛНЕНИЕ ЗАПРОСОВ С ПОМОЩЬЮ  КОМАНД - COUNT и COMPLEX SELECT

// COUNT пример считаем количество записей world
$query = ["hello" => "world"];
$command = new MongoDB\\Driver\\Command(["count" => "collection", "query" => $query]);
try {
    $result = $mongo->executeCommand("mydb", $command);
    $res = current($result->toArray());
    $count = $res->n;
    echo $count;
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}


// COMPLEX SELECT (это пример, результат этого запроса будет пустой)
$command = new MongoDB\\Driver\\Command([
    'aggregate' => 'collection',
    'pipeline' => [
        ['$match' => [
            "hello" => "world"
        ]],
        ['$project' => [
            "hello" => 1
        ]],
        ['$group' => [
            '_id' => '$hello', 'sum' => ['$sum' => '$world']
        ]],
        ['$skip' => 1],
        ['$limit' => 1],
        ['$sort' => [
            'hello' => 1
        ]],
    ],
    'cursor' => new stdClass,
]);
$cursor = $mongo->executeCommand('mydb', $command);
foreach ($cursor as $document) {
    echo "<pre>";
    var_dump($document);
    echo "</pre>";
}


//еще хотелось бы показать нюансы вставки и преобразования дат 

// ВСТАВИТЬ ТЕКУЩУЮ ДАТУ
$milliseconds = round(microtime(true) * 1000); // теперь это миллисекунды
$document = ["date" => new MongoDB\\BSON\\UTCDateTime($milliseconds)];
$bulk = new MongoDB\\Driver\\BulkWrite;
$id = $bulk->insert($document);
try {
    $result = $mongo->executeBulkWrite('mydb.collection', $bulk);
    echo (string)$id;
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}


// ИЗВЛЕКАЕМ ДАТУ И ДЕЛАЕМ ЧИТАБЕЛЬНОЙ
// раньше был new Mongoid($_id)
// теперь это new MongoDB\\BSON\\ObjectId($_id)
$filter = ['_id' => new MongoDB\\BSON\\ObjectId('568991464c20200df6792a39')];
$options = ['limit' => 1];
$query = new MongoDB\\Driver\\Query($filter, $options);
try {
    $cursor = $mongo->executeQuery('mydb.collection', $query);
    // если хотите работать как с массивом а не обьектом, то приходится преобразовывать =(
    $cursor = MongoDB\\BSON\\fromPHP($cursor->toArray());
    $cursor = json_decode(MongoDB\\BSON\\toJSON($cursor), true);
    //
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}
$res = current($cursor);
// можно так
$date = date('Y-m-d H:m:s', $res['date']['$date'] / 1000 );
echo $date.'<br/>';
// можно так
$d = new MongoDB\\BSON\\UTCDateTime($res['date']['$date']);
$datetime = $d->toDateTime();
$date = $datetime->format('Y-m-d H:m:s');
echo $date.'<br/>';


// Автоинкремент поля Mongodb через findAndModify
// http://veselov.sumy.ua/1960-avtoinkrement-polya-mongodb-na-php.html
$command = new MongoDB\\Driver\\Command([
    'findAndModify' => 'collection_counters', 
    'query' => ['field' => 'user_id'],
    'update' => ['$inc' => ['nextId' => 1]],
    "new" => true
]);
try {
    $result = $mongo->executeCommand("mydb", $command);
    $num = $result->toArray();
    $num = $num['nextId'];
    // дальше добавляем сам документ
    // ..
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}

 
// Множественный INSERT batchInsert как и UPDATE и DELETE 
// выполняется аналогично insert
$bulk = new MongoDB\\Driver\\BulkWrite;
$bulk->insert(["hello" => "world"]);
$bulk->insert(["hello1" => "world1"]);
$bulk->insert(["hello2" => "world3"]);
try {
    $result = $mongo->executeBulkWrite('mydb.collection', $bulk);
} catch (MongoDB\\Driver\\Exception\\Exception $e) {
    echo $e->getMessage(), "\\n";
}

// преобразование даты для выборки по дате 
// ранее было new MongoDate( time() )
// теперь new MongoDB\\BSON\\UTCDateTime(  time() * 1000 )
$dateTime = new MongoDB\\BSON\\UTCDateTime(strtotime(date('Y-m-d H:m:s', time())).'000');
$filter = [
    'date' => [
        '$gte' => new MongoDB\\BSON\\UTCDateTime(strtotime("{$year}-{$month}-01").'000'),
        '$lt' => new MongoDB\\BSON\\UTCDateTime(strtotime(date('Y-m-d H:m:s')).'000')
    ]
];


// Было
// new MongoRegex("/$text/i"))
// стало
// new MongoDB\\BSON\\Regex($text, 'i'))


// И еще пример для размышления =)
$filter = [];
$options = [];
$query = new MongoDB\\Driver\\Query($filter, $options);
$cursor = $mongo->executeQuery( 'mydb.collection', $query);
$cursor->setTypeMap(['root' => 'array']); // выводим как массив
// формируем массив в нужном для нас порядке
foreach ( $cursor as $doc ) {
    $id = (string)$doc['_id'];
    $res[$id] = $doc;
    unset($res[$id]['_id']);
}
echo "<pre>";
print_r($res);
echo "</pre>";

echo '<br/>ok';
```

  
Ну вот вроде как и разобрались с основным представлением о том как выглядит новый **php mongodb driver**.
