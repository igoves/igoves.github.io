---
title: "Пишем загрузку изображения на php+ajax+jquery+jquery.form"
date: ""
categories: 
  - "php"
tags: 
  - "upload-php-ajax-jquery-jqueryform"
---

![Пишем загрузку изображения на php+ajax+jquery+jquery.form](images/1314387003_75.jpg "Пишем загрузку изображения на php+ajax+jquery+jquery.form")

  
Для начала делаем форму upload.html (в контейнере preview будет показываться миниатюрка):  

```
<form id="imageform" method="post" enctype="multipart/form-data" action='ajaximage.php'>Загрузить пикчу <input type="file" name="photoimg" id="photoimg" /><div id='preview'></div></form>
```

  
Моторчик который обрабатывает форму ajaximage.php:  

```
<?php$path = "uploads/"; // куда заливаем$valid_formats = array("jpg", "png", "gif", "bmp","jpeg"); // допустимые форматыif(isset($_POST) and $_SERVER['REQUEST_METHOD'] == "POST") // пришел запрос{    $name = $_FILES['photoimg']['name']; // имя файла    $size = $_FILES['photoimg']['size']; // размер файла    if(strlen($name))    {        list($txt, $ext) = explode(".", $name); // разбиваем на имя и формат        if(in_array($ext,$valid_formats))    // смотрим формат такой как мы разрешили?!        {            if($size<(1024*1024)) // Ограничиваем размер файла в 1 мб             {             $actual_image_name = time().$session_id.".".$ext; // задаем уникальное имя файлику             $tmp = $_FILES['photoimg']['tmp_name'];            if(move_uploaded_file($tmp, $path.$actual_image_name)) // переносим файл с tmp в наш каталог             {                echo "<img src='uploads/".$actual_image_name."' class='preview'>"; // показываем привьюшку             }            else echo "облом";             }            else echo "Размер файла больше одного мб";         }        else echo "Формат не подходит.";     }    else echo "Пожалуйста выбирите изображение!";    exit;}
```

  
  
А что бы это все было аяксовым подключаем jquery и jquery.form (http://jquery.malsup.com/form/)  

```
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.5/jquery.min.js"></script><script type="text/javascript" src="jquery.form.js"></script>
```

  
И последний штрих:  

```
<script> $(document).ready(function() //готов {  $('#photoimg').live('change', function() //photoimg изменился?! {  $("#preview").html(''); // чистим preview $("#preview").html('<img src="loader.gif" alt="Uploading...."/>'); //показываем картинку загрузки $("#imageform").ajaxForm( //отправляем аякс запрос (тут уже действует jquery.fomr { target: '#preview' }).submit(); }); }); </script>
```
