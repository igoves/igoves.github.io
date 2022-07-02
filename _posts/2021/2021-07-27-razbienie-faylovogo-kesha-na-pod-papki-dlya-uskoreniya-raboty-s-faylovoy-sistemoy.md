---
title: "Разбиение файлового кэша на под папки, для ускорения работы с файловой системой"
categories: 
  - "php"
---

Доступ к файлам существенно замедляется если в директории становится очень много файлов (чем больше файлов, тем меньше скорость).  
  
Поэтому делят на папки вот так:

```
<?php
function saveCache($name, $data) {
	$hash = sha1($name);
	$chunks = str_split($hash, 4);
	$cache_dir = CACHE_DIR.'/'.$chunks[0].'/'.$chunks[1];
	if (!is_dir($cache_dir)) mkdir($cache_dir, 0775, true);
	return file_put_contents($cache_dir.'/'.$hash, serialize($data));
}
```
