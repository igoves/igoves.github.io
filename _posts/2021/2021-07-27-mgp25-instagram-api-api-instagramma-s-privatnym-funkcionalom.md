---
title: "mgp25/Instagram-API - API инстаграмма с приватным функционалом"
date: ""
categories: 
  - "php"
---

Он имеет почти все функции, которые есть в приложении Instagram, включая загрузку мультимедиа, обмен сообщениями, истории и многое другое.  
Пример загрузки фото

```
$metadata = [
              'caption' => 'My awesome caption',
              'location' => $location, // $location must be an instance of /Model/Location class
            ];

// if you want only a caption, you can simply do this:
$metadata = ['caption' => 'My awesome caption'];

$ig->timeline->uploadPhoto($photoFilename, $metadata);
```

  
[https://github.com/mgp25/Instagram-API](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21ncDI1L0luc3RhZ3JhbS1BUEk%3D)
