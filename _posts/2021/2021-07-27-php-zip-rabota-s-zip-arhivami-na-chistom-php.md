---
title: "php-zip - работа с zip архивами на чистом php"
date: ""
categories: 
  - "php"
---

Библиотека поддерживает: P64, zipalign, Traditional PKWARE Encryption and WinZIP AES Encryption.  
  
Пример открыть архив  

```
$zipFile = \\PhpZip\\ZipFile::openFromFile($filename);
```

  
Пример получить список файлов  

```
$listFiles = $zipFile->getListFiles();
```

  
[https://github.com/Ne-Lexa/php-zip](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL05lLUxleGEvcGhwLXppcA%3D%3D)
