---
title: "PHP функция проверки существования вебмани кошелька"
categories: 
  - "php"
---

```
<?phpfunction checkPurce( $purce ) { 	if ( strlen($purce) == 13 ) {		$handle = fopen("http://passport.webmoney.ru/asp/CertView.asp?purse=".$purce, "r");		$buffer = '';		while (!feof($handle)) {			$buffer .= fgets($handle, 4096);			$present = substr_count($buffer, $purce);		}		fclose($handle);		if( $present != 0 ) {			return '{ "status" : "1" }';		} else {			return '{ "status" : "0" }';		}	} else {		return '{ "status" : "0" }';	}}echo checkPurce('R301381303111');
```

  
работает с этим http://passport.webmoney.ru/asp/VerifyWMID.asp
