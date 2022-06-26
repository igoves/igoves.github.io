---
title: "Транзакции MySQL"
date: ""
categories: 
  - "note"
tags: 
  - "mysql"
  - "transactions"
---

Задача транзакций создать строгую целостность информации. Транзакции обеспечивают гарантию того, что незаконченные обновления или искаженные действия не будут фиксироваться в базе данных; серверу предоставляется возможность выполнить автоматический откат, и база данных будет сохранена.  
  
Создадим таблицу balance

```
CREATE TABLE `balance` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `action` varchar(255) NOT NULL,
  `val` int(11) NOT NULL,
  `total` int(11) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

  
Проверяем вставку **без транзакции**

```
<h1>Тест транзакций MySQL 5.6</h1>
<?php
$db = mysqli_connect('localhost', 'root', '', 'transactions');
if (mysqli_connect_errno()) {
    printf("Ошибка соединения: ", mysqli_connect_error());
    die();
}
$action[] = array( 'act' => '+', 'val' => 10 );
$action[] = array( 'act' => '+', 'val' => 20 );
$action[] = array( 'act' => '-', 'val' => 5 );
$action[] = array( 'act' => '+', 'val' => 10 );
$i = 0;
// БЕЗ ТРАНЗАКЦИЙ
foreach ( $action as $key => $value ) {
	$i ++;
	// имитируем долгое выполнение на 2-ой вставке ( при этом сервер выключаю )
	if ( $i == 2 ) sleep(20);
	// получить последний total
	$row = mysqli_fetch_assoc($db->query("SELECT total FROM balance ORDER BY id DESC LIMIT 1"));
	$total = $row['total'];
	$db->query("
		INSERT INTO 
			balance
		SET
			action = '{$value['act']}',
			val = {$value['val']},
			total = $total {$value['act']} {$value['val']}
	");
	print_r($value);
}
echo '<br/>- запросы выполнены';
$db->close();
```

  
// Резльтат: выключив на паузе mysql, вставилось в таблицу balance одна запись - целостность нарушена ( в реальной жизни это могло бы например значить, что у кого-то деньги с баланса сняли, а кому-то зачислить не успели из за сбоя)  
  
Проверяем вставку **с транзакцией**

```
<h1>Тест транзакций MySQL 5.6</h1>
<?php
$db = mysqli_connect('localhost', 'root', '', 'transactions');
if (mysqli_connect_errno()) {
    printf("Ошибка соединения: ", mysqli_connect_error());
    die();
}
$action[] = array( 'act' => '+', 'val' => 10 );
$action[] = array( 'act' => '+', 'val' => 20 );
$action[] = array( 'act' => '-', 'val' => 5 );
$action[] = array( 'act' => '+', 'val' => 10 );
$i = 0;
// С ТРАНЗАКЦИЕЙ
$db->autocommit(FALSE);
foreach ( $action as $key => $value ) {
	$i ++;
	// имитируем долгое выполнение на 2-ой вставке (выключаем mysql принудительно)
	if ( $i == 2 ) sleep(20);
	// получить последний total
	$row = mysqli_fetch_assoc($db->query("SELECT total FROM balance ORDER BY id DESC LIMIT 1"));
	$total = $row['total'];
	$db->query("
		INSERT INTO 
			balance
		SET
			action = '{$value['act']}',
			val = {$value['val']},
			total = $total {$value['act']} {$value['val']}
	");
	print_r($value);
}
if ( ! $db->commit() ) {
	$db->rollback();
	echo '<br/>- возникла ошибка откат запросов';
	die();
}
echo '<br/>- запросы выполнены';
$db->close();
```

  
// Результат: выключив mysql коммит не срабатывает и ни один запрос из транзакции не добавляется в бд. Целостность не нарушена ( в реальной жизни это могло бы например значить, что у кого-то деньги с баланса сняли, произошел сбой, но так как commit не выполнился, то rollback откатывает до начального состояния).  
**COMMIT** - для записи изменений на диск.  
**ROLLBACK** \- игнорирует изменения, произведенные с начала транзакции.
