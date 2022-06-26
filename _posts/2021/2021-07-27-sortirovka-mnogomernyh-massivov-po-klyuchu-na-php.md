---
title: "Сортировка многомерных массивов по ключу на PHP"
categories: 
  - "php"
tags: 
  - "klyuch"
  - "massiv"
  - "sortirovka"
---

```
$data=array(	array('text'=>'str1', 'year'=>'2010', 'author'=>10),	array('text'=>'str2', 'year'=>'2011', 'author'=>10),	array('text'=>'str3', 'year'=>'2009', 'author'=>20),	array('text'=>'str4', 'year'=>'2010', 'author'=>30),	array('text'=>'str5', 'year'=>'2010', 'author'=>20),	array('text'=>'str6', 'year'=>'2011', 'author'=>10),	array('text'=>'str7', 'year'=>'2011', 'author'=>20),	array('text'=>'str8', 'year'=>'2009', 'author'=>20),);
```

  

```
$data_author=array();foreach($data as $key=>$arr){	$data_author[$key]=$arr['author'];} $data_year=array();foreach($data as $key=>$arr){	$data_year[$key]=$arr['year'];} array_multisort($data_year, SORT_NUMERIC, $data_author, $data);var_export($data);
```

  

```
array(  0 => array('text' => 'str3', 'year' => '2009', 'author' => 20, ),  1 => array('text' => 'str8', 'year' => '2009', 'author' => 20, ),  2 => array('text' => 'str1', 'year' => '2010', 'author' => 10, ),  3 => array('text' => 'str5', 'year' => '2010', 'author' => 20, ),  4 => array('text' => 'str4', 'year' => '2010', 'author' => 30, ),  5 => array('text' => 'str2', 'year' => '2011', 'author' => 10, ),  6 => array('text' => 'str6', 'year' => '2011', 'author' => 10, ),  7 => array('text' => 'str7', 'year' => '2011', 'author' => 20, ),);
```
