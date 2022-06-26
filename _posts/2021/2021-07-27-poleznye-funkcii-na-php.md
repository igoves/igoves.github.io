---
title: "Полезные функции на php"
date: ""
categories: 
  - "php"
tags: 
  - "php"
  - "regulyarnye-vyrajeniya"
  - "chastye-funkcii"
---

![Полезные функции на php](images/1290020377_untitled-1.jpg "Полезные функции на php")

  
**Функция для обработки текста**  

```
function ProcessText($text){    $text = trim($text); // удаляем пробелы по бокам    $text = stripslashes($text); // удаляем слэши    $text = htmlspecialchars($text); // переводим HTML в текст    $text = preg_replace("/ +/", " ", $text); // множественные пробелы заменяем на одинарные    $text = preg_replace("/(\\r\\n){3,}/", "\\r\\n\\r\\n", $text); // убираем лишние переводы строк (больше 1 строки)    $test = nl2br ($text); // заменяем переводы строк на тег    $text = preg_replace("/^\\"([^\\"]+[^=><])\\"/u", "$1«$2»", $text); // ставим людские кавычки    $text = preg_replace("/(«){2,}/","«",$text); // убираем лишние левые кавычки (больше 1 кавычки)    $text = preg_replace("/(»){2,}/","»",$text); // убираем лишние правые кавычки (больше 1 кавычки)          $text = preg_replace("/(\\r\\n){2,}/u", "</p><p />", $text); // ставим абзацы    return $text; //возвращаем переменную}
```

  
  
**Функции для работы с файлами**  

```
// Извлечение контента файлаfunction Get($file){      return file_get_contents($file);}
```

  
  
// Сохранение контента в файл  

```
function Save($file, $content){      return (file_put_contents($file, stripslashes($content)));}
```

  
  
**Функция для отправки письма**  
// Входные данные: адрес получателя, адрес отправителя, тема письма, текст письма, имя отправителя  

```
function SendEmail($toEmail, $fromEmail, $subject, $content, $from){      // Обработка темы      $subject = "=?utf-8?b?" . base64_encode($subject) . "?=";      // Формирование заголовков      $headers = "MIME-Version: 1.0\\r\\n";      $headers .= "Content-type: text/html; charset=utf-8\\r\\n";      $headers .= "From: =?utf-8?b?" . base64_encode($from) . "?= ";      return (mail($toEmail, $subject, $content, $headers));}
```

  
  
Фильтруем нулевой байт  

```
$mode = preg_replace('/\\0/s', '', $mode); 
```

  
  
И еще чуток  

```
     $result = stripslashes($result); // удаляем слэши    $result = str_replace('#39;', '', $result); // удаляем одинарные кавычки    $result = str_replace('&quot;', '', $result); // удаляем двойные кавычки    $result = str_replace('&amp;', '', $result); // удаляем амперсанд    $result = preg_replace('/([?!:^~|@№$–=+*&%.,;\\[\\]&lt;&gt;()_—«»#\\/]+)/', '', $result); // удаляем недоспустимые символы    $result = trim($result); // удаляем пробелы по бокам    $result = preg_replace('/ +/', '-', $result); // пробелы заменяем на минусы    $result = preg_replace('/-+/', '-', $result); // удаляем лишние минусы    $result = preg_replace('/([-]*)(.+)([-]*)/', '\\\\2', $result); // удаляем лишние минусы
```
