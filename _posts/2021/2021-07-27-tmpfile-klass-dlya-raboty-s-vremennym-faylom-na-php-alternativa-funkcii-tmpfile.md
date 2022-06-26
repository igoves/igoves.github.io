---
title: "tmpfile - класс для работы с временным файлом на PHP альтернатива функции tmpfile"
date: ""
categories: 
  - "php"
---

```
<?php

require __DIR__ . '/vendor/autoload.php';

// Создать временный файл
$tmpfile = new tmpfile;

// Сразу с контентом
$tmpfile = new tmpfile('Hello, world!');

/* ... */

// Записать в файл
$tmpfile->write('abc');

// Дописать в конец
$tmpfile->write('def', FILE_APPEND);

// Способ короче
$tmpfile->puts('def');

// Прочитать весь файл
$tmpfile->read();

// Какую-то часть
$tmpfile->read(7, 5);

// Удалить файл
$tmpfile->delete();

/* ... */

// Передать URI в объект
new SplFileInfo($tmpfile);

// Переместить в другую папку
rename($tmpfile, __DIR__ . '/picture.jpg');

// Проверить на наличие
file_exists($tmpfile);
```

  
[https://github.com/denisyukphp/tmpfile](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2RlbmlzeXVrcGhwL3RtcGZpbGU%3D)
