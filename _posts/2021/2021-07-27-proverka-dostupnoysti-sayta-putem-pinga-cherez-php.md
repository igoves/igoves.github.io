---
title: "Проверка доступнойсти сайта путем пинга через PHP"
categories: 
  - "php"
---

Функция пинга  

```
public function ping($link, $poort){
	$paketten=5;
	$timeout=0.5;
	for ($i=0;$i<=$paketten;$i++){
		$a=substr(microtime(),11,9)+substr(microtime(),0,10);
		$fs = @fsockopen($link, $poort, $errno, $errstr, $timeout);
		$b=substr(microtime(),11,9)+substr(microtime(),0,10);
		if (!$fs){
			return FALSE;
		}
		$pingtijd=$pingtijd+round(($b-$a)*1000);
		@fclose($fs);
	}
	if(($pingtijd/$paketten)<3){
		$pingtijd="2";
	}else {
		$pingtijd=($pingtijd/$paketten);
	}
	return $pingtijd;
}
```
