---
title: "Прячим сапачку от поисковиков"
categories: 
  - "php"
tags: 
  - "hide"
  - "sape"
  - "poiskoviki"
---

Скажем так если у Вас качественный СДЛ и на нем стоит биржа с правильно расставленными ссылками, то поисковик ничего Вашему драгоценному сайту не сделает.  
  
Если же он немножко похож на ГС, то стоит задуматься о том, что бы не палиться о продажности своего сайта, так как санкции будут жестоки и беспощадны.  
  
И так, есть страница с продажной ссылкой site.ua/link.html бот подставляет, что то вида site.ua/link.html?trololo (это не догма, может быть любой другой мусор) и смотрит есть ли там эта самая ссылка, если ее нет, значит Вы спалились...  
  
Зная этот момент, просто делаем так чтобы саповский скрипт правильно сравнивал полученный урл с имеющемся с базой линков.  
  
. Создайте в саповской папке файл sape\_venality\_name.php:  

```
<?php $sape_venality_name=array(); # Документы, работающие с глобалом GET:$allowed_pages=array("key.php","ping","remoute"); # Разрешённые переменные в УРле иных документов:$allowed_var=array(""); $tm=explode("?",$_SERVER['REQUEST_URI']);if (isset($tm[1]) and $tm[0]==str_replace($allowed_pages,"",$tm[0])) {$k=preg_match_all("/(.*)=(.*)\\&/Uis",$tm[1]."&",$am);$bm=array();for ($i=0; $i < $k; $i++) {if ($am[2][$i]=="" or !in_array($am[1][$i],$allowed_var))continue;$bm[]=$am[1][$i]."=".$am[2][$i];}$tm[1]=implode("&",$bm);$sape_venality_name['request_uri']=$_SERVER['REQUEST_URI']=($tm[1]=="") ? $tm[0]: implode("?",$tm);} ?>
```

  
2\. Код вызова, используемый на сайте:  

```
<?php      if (!defined('_SAPE_USER')){        define('_SAPE_USER', 'идентификатор');      }     require_once($_SERVER['DOCUMENT_ROOT'].'/'._SAPE_USER.'/sape.php');      $sape = new SAPE_client();?>
```

  
замените на следующий:  

```
<?php      if (!defined('_SAPE_USER')){        define('_SAPE_USER', 'идентификатор');      }     require_once($_SERVER['DOCUMENT_ROOT'].'/'._SAPE_USER.'/sape.php');      require_once($_SERVER['DOCUMENT_ROOT'].'/'._SAPE_USER.'/sape_venality_name.php');      $sape=new SAPE_client($sape_venality_name);?>
```

  
Имейте в виду, что данная инструкция не гарантирует 100% скрытие ссылок. Какие методы применяет Яндекс никому неизвестно.
