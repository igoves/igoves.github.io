---
title: "Генерация нового названия, если файл с таким именем уже существует"
categories: 
  - "php"
---

```
function file_newname($path, $filename){    if ($pos = strrpos($filename, '.')) {           $name = substr($filename, 0, $pos);           $ext = substr($filename, $pos);    } else {           $name = $filename;    }    $newpath = $path.'/'.$filename;    $newname = $filename;    $counter = 0;    while (file_exists($newpath)) {           $newname = $name .'_'. $counter . $ext;           $newpath = $path.'/'.$newname;           $counter++;     }    return $newname;}
```

**Результат**  
myfile.jpg  
myfile\_0.jpg  
myfile\_1.jpg
