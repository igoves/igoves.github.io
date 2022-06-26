---
title: "CssToInlineStyles - php класс для встраивания стилей в страницу удобно для создания html писем"
date: ""
categories: 
  - "css"
---

Пример

```
use TijsVerkoyen\\CssToInlineStyles\\CssToInlineStyles;

// create instance
$cssToInlineStyles = new CssToInlineStyles();

$html = file_get_contents(__DIR__ . '/examples/sumo/index.htm');
$css = file_get_contents(__DIR__ . '/examples/sumo/style.css');

// output
echo $cssToInlineStyles->convert(
    $html,
    $css
);
```

  
[https://github.com/tijsverkoyen/CssToInlineStyles](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3RpanN2ZXJrb3llbi9Dc3NUb0lubGluZVN0eWxlcw%3D%3D)
