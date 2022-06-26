---
title: "GifCreator - php класс для создание гифки из нескольких изображений"
categories: 
  - "php"
---

Пример

```
// Create an array containing file paths, resource var (initialized with imagecreatefromXXX), 
// image URLs or even binary code from image files.
// All sorted in order to appear.
$frames = array(
    imagecreatefrompng("/../images/pic1.png"), // Resource var
    "/../images/pic2.png", // Image file path
    file_get_contents("/../images/pic3.jpg"), // Binary source code
    'http://thisisafakedomain.com/images/pic4.jpg', // URL
);

// Create an array containing the duration (in millisecond) of each frames (in order too)
$durations = array(40, 80, 40, 20);

// Initialize and create the GIF !
$gc = new GifCreator();
$gc->create($frames, $durations, 5);
```

Поличить результат

```
$gifBinary = $gc->getGif();
```

  
[https://github.com/Sybio/GifCreator](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1N5YmlvL0dpZkNyZWF0b3I%3D)
