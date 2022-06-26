---
title: "Кэширование на WP"
date: "2010-03-05"
categories: 
  - "php"
tags: 
  - "wp"
  - "kesh"
---

заменить index.php и создать для записи каталог в корне cache и поставить chmod 777

```

<?php
$filename = 'cache/'.md5($_SERVER['REQUEST_URI']).'.html'; 
 
$cached = false; 
 
if (file_exists($filename)) {
if ((time()-filemtime($filename))<6160) {
$cached = true;
} else {
unlink($filename);
$cached = false;
}
} 
 
if ($cached) {
readfile($filename);
} else {
ob_start(); 
 
// WP
define('WP_USE_THEMES', true);
require('./wp-blog-header.php');
// 
 
$text = ob_get_clean(); 
 
$fh = fopen($filename, 'w+');
fwrite($fh, $text);
fclose($fh); 
 
echo $text;
}
?>
```
