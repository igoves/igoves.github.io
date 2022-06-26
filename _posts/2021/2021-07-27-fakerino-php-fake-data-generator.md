---
title: "Fakerino - PHP Fake data генератор"
date: ""
categories: 
  - "php"
---

**Возможности**  
\- смешанные данные (e.g. person: name, surname, hobby, country, ... ).  
\- единичные значения ( имя, фамилия, число, текст, ...).  
\- разные языки  
\- regular expression data (e.g. url => \\'/www\\\\.\\\\w+\\\\.com/\\').  
\- даты  
\- поддерживает Twig string (например Hello Mr {{ surname }})  
\- поддерживает JSON, array и string вывод.  
\- поддерживает array, Yaml, XML, PHP, Txt и Ini конфигурации.  
\- доступен из командой строки.  
  
**Пример**  

```
<?php
require ('vendor/autoload.php'); 
use Fakerino\\Fakerino;

$fakerino = Fakerino::create();
echo $fakerino->fake('Surname')->toJson(); //["Donovan"]
echo $fakerino->fake('nameFemale'); //Alice
echo $fakerino->fake('/www\\.\\w+\\.com/'); //www.nikdjap.com
echo $fakerino->fake('nameMale')->num(3); //Bob Jack Rick
echo $fakerino->fake(array('nameMale', 'Surname'))->num(3)->toJson(); //[["Simon","Rodgers"],["Dean","Smith"],["Anthony","Bauman"]]
```

  
[https://github.com/Fakerino/Fakerino](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0Zha2VyaW5vL0Zha2VyaW5v)
