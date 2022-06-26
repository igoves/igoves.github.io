---
title: "Создаём зависимые списки с помощью jQuery и AJAX"
categories: 
  - "js"
---

![Создаём зависимые списки с помощью jQuery и AJAX](images/1385319650_untitled-25.jpg "Создаём зависимые списки с помощью jQuery и AJAX")

  
Для начала нам понадобится список областей и городов в формате  

```
<?php // файл city.php $city = array (  'Москва и Московская обл.' => array (    0 => 'Москва',    1 => 'Абрамцево',    // ...  ),  'Санкт-Петербург и область' => array (    0 => 'Санкт-Петербург',    1 => 'Александровская',    // ...  ),  // ...); ?>
```

  
Создаём два select-а, в одном будут области, в другой будут подгружаться города  

```
<select name="region" onchange="loadCity(this)">    <option></option>     <?php // заполняем список областей    foreach ($city as $region => $cityList)    {        echo '<option value="' . $region . '">' . $region . '</option>' . "\\n";    }    ?> </select> <select name="city" disabled="disabled">    <option>Выберите область</option></select>
```

  
При выборе области, сработает функция loadCity, которая подгрузит список городов. Определим её:  

```
function loadCity(select){    var citySelect = $('select[name="city"]');     // послыаем AJAX запрос, который вернёт список городов для выбранной области    $.getJSON('index.php', {action:'getCity', region:select.value}, function(cityList){        citySelect.html(''); // очищаем список городов         // заполняем список городов новыми пришедшими данными        $.each(cityList, function(i){            citySelect.append('<option value="' + i + '">' + this + '</option>');        });    });}
```

  
Ну и php скрипт который отдаст в JSON формате список городов конкретной области:  

```
<?php // файл index.php require_once('city.php'); if (isset($_GET['action']) && $_GET['action'] == 'getCity'){    if (isset($city[$_GET['region']]))    {        echo json_encode($city[$_GET['region']]); // возвращаем данные в JSON формате;    }    else    {        echo json_encode(array('Выберите область'));    }     exit;} ?>
```

  
Все файлы должны быть в кодировке UTF-8 without BOM, а сервер должен отдавать заголовки с правильно указанным charset (для этого в исходниках есть файл .htaccess)  
[СКАЧАТЬ](https://dev.xfor.top/go/aHR0cDovL3hhbmRlYWR4LnJ1L2V4YW1wbGVzL2RlcGVuZGVudC1zZWxlY3Qvc291cmNlLnJhcg%3D%3D)
