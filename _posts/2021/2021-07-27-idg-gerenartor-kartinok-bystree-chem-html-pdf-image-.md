---
title: "idg - геренартор картинок ( быстрее чем html->pdf->image )"
categories: 
  - "php"
---

Требования Imagick. Можно создавать такие изображения:  

[![idg - геренартор картинок ( быстрее чем html->pdf->image )](https://camo.githubusercontent.com/404d0311739db07c47bc5a50196ab0d4018a4802/687474703a2f2f6e696b69746368656e6b6f2e72752f6964672f6578616d706c65312e706e67 "idg - геренартор картинок ( быстрее чем html->pdf->image )")](https://camo.githubusercontent.com/404d0311739db07c47bc5a50196ab0d4018a4802/687474703a2f2f6e696b69746368656e6b6f2e72752f6964672f6578616d706c65312e706e67)

  

```
<?php

require_once __DIR__ . '/vendor/autoload.php';
// font for example
$fontRegular = 'RobotoCondensed-Regular.ttf';

$idg = new \\Idg\\Idg(1000, 3000, null, new ImagickPixel('#fff'));
$idg->beginDocument(40, 30, 40, 30);
 $idg->beginRow();
        $idg->beginColumn(300);
            $idg->image('test_image.jpg');
            $idg->beginBlock()->setLeft(20);
                $idg->text('Figure 1. Dolore eu fugiat nulla pariatur.')
                ->setFont($fontRegular)->setFontSize(14)->setTextColor('#555');
            $idg->endBlock();
        $idg->endColumn();
        $idg->beginColumn(600);
                $idg->text('Lorem ipsum dolor sit amet, 
                consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate 
                velit esse cillum dolore eu fugiat nulla pariatur. 
                Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.')
                    ->setFont($fontRegular);
        $idg->endColumn();
        $idg->endRow();
$idg->endDocument();
$idg->compose();

header('Content-Type: image/' . $idg->getCanvas()->getImageFormat());
print $idg->getImageBlob();
```

  
[https://github.com/NikitchenkoSergey/idg](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL05pa2l0Y2hlbmtvU2VyZ2V5L2lkZw%3D%3D)
