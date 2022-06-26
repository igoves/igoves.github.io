---
title: "dejurin/php-google-translate-for-free - пхп библиотека для работы с гугл переводчиком"
date: ""
categories: 
  - "php"
---

```
$source = 'en';
$target = 'ru';
$attempts = 5;
$arr = array('hello','world');

$tr = new GoogleTranslateForFree();
$result = $tr->translate($source, $target, $arr, $attempts);

var_dump($result); 

/*
	array(2) {
	  [0]=>
	  string(24) "Здравствуйте"
	  [1]=>
	  string(6) "Мир"
	}

*/
```

  
[https://github.com/dejurin/php-google-translate-for-free](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2RlanVyaW4vcGhwLWdvb2dsZS10cmFuc2xhdGUtZm9yLWZyZWU%3D)
