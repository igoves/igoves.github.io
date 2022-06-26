---
title: "JBZoo Image - php библиотека для манипуляции изображениями"
date: ""
categories: 
  - "php"
---

Пример использования  

```
use JBZoo\\Image\\Image;
use JBZoo\\Image\\Filter;
use JBZoo\\Image\\Exception;

try { // Error handling

    $img = (new Image('./some-path/image.jpg'))     // You can load an image when you instantiate a new Image object
        ->loadFile('./some-path/another-path.jpg')  // Load another file (replace internal state)

        // Saving
        ->save()   // Images must be saved after you manipulate them. To save your changes to the original file.
        ->save(90) // Specify quality (0 to 100)

        // Save as new file
        ->saveAs('./some-path/new-image.jpg')     // Alternatively, you can specify a new filename
        ->saveAs('./some-path/new-image.jpg', 90) // You can specify quality as a second parameter in percents within range 0-100
        ->saveAs('./some-path/new-image.png')     // Or convert it into another format by extention (gif|jpeg|png)

        // Resizing
        ->resize(320, 200)          // Resize the image to 320x200
        ->thumbnail(100, 75)        // Trim the image and resize to exactly 100x75 (crop CENTER if needed)
        ->thumbnail(100, 75, true)  // Trim the image and resize to exactly 100x75 (crop TOP if needed)
        ->fitToWidth(320)           // Shrink the image to the specified width while maintaining proportion (width)
        ->fitToHeight(200)          // Shrink the image to the specified height while maintaining proportion (height)
        ->bestFit(500, 500)         // Shrink the image proportionally to fit inside a 500x500 box
        ->crop(100, 100, 400, 400)  // Crop a portion of the image from left, top, right, bottom

        // Filters
        ->addFilter('sepia')                        // Sepia effect (simulated)
        ->addFilter('grayscale')                    // Grayscale
        ->addFilter('desaturate', 50)               // Desaturate
        ->addFilter('pixelate', 8)                  // Pixelate using 8px blocks
        ->addFilter('edges')                        // Edges filter
        ->addFilter('emboss')                       // Emboss filter
        ->addFilter('invert')                       // Invert colors
        ->addFilter('blur', Filter::BLUR_SEL)       // Selective blur (one pass)
        ->addFilter('blur', Filter::BLUR_GAUS, 2)   // Gaussian blur (two passes)
        ->addFilter('brightness', 100)              // Adjust Brightness (-255 to 255)
        ->addFilter('contrast', 50)                 // Adjust Contrast (-100 to 100)
        ->addFilter('colorize', '#FF0000', .5)      // Colorize red at 50% opacity
        ->addFilter('meanRemove')                   // Mean removal filter
        ->addFilter('smooth', 5)                    // Smooth filter (-10 to 10)
        ->addFilter('opacity', .5)                  // Change opacity
        ->addFilter('rotate', 90)                   // Rotate the image 90 degrees clockwise
        ->addFilter('flip', 'x')                    // Flip the image horizontally
        ->addFilter('flip', 'y')                    // Flip the image vertically
        ->addFilter('flip', 'xy')                   // Flip the image horizontally and vertically
        ->addFilter('fill', '#fff')                 // Fill image with white color

        // Custom filter handler
        ->addFilter(function ($image, $blockSize) {
            imagefilter($image, IMG_FILTER_PIXELATE, $blockSize, true);
        }, 2) // $blockSize = 2

        // Overlay watermark.png at 50% opacity at the bottom-right of the image with a 10 pixel horz and vert margin
        ->overlay('./image/watermark.png', 'bottom right', .5, -10, -10)

        // Other
        ->create(200, 100, '#000') // Create empty image 200x100 with black background
        ->setQuality(95)           // Set new internal quality state
        ->autoOrient()             // Adjust the orientation if needed (physically rotates/flips the image based on its EXIF 'Orientation' property)
    ;

} catch(Exception $e) {
    echo 'Error: ' . $e->getMessage();
}
```

  
Методы создающие изображения  

```
// Filename
$img = new Image('./path/to/image.png');

// Base64 format
$img = new Image('data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==');

// Image string
$img = new Image('R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==');

// Some binary data
$imgBin = base64_decode('R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==');
$img = new Image($imgBin);

// Resource
$imgRes = imagecreatefromjpeg('./some-image.jpeg');
$img = new Image($imgRes);
```

и тд. и тп.  
[https://github.com/JBZoo/Image](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0pCWm9vL0ltYWdl)
