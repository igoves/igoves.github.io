---
title: "PHP. Конвертируем PDF -> JPG. Получаем возраст. Распаковываем zip арихив."
date: ""
categories: 
  - "php"
---

Конвертируем PDF -> JPG  

```
function pdfToJpg($pdf, $jpg) {    $im = new Imagick();    $im->setResolution(300,300);    $im->readimage($pdf);    $im->setImageFormat('jpeg');    $im->writeImage($jpg);    $im->clear();    $im->destroy();}
```

  
  
Получаем возраст  

```
function getAge($birthdate = '0000-00-00') {    if ($birthdate == '0000-00-00') return 'Unknown';    $bits = explode('-', $birthdate);    $age = date('Y') - $bits[0] - 1;    $arr[1] = 'm';    $arr[2] = 'd';    for ($i = 1; $arr[$i]; $i++) {        $n = date($arr[$i]);        if ($n < $bits[$i])            break;        if ($n > $bits[$i]) {            ++$age;            break;        }    }    return $age;}
```

  
  
Распаковываем zip архив  

```
function unzipArchive($file, $destinationFolder){	// create ZipArchive object	$zip = new ZipArchive() ;	// open archive	if ($zip->open($file) !== TRUE) {		die ('Could not open archive');	}	// extract it's content to destination folder	$zip->extractTo($destinationFolder);	// close archive	$zip->close();}
```
