---
title: "Сниппеты PHP"
date: "2009-11-13"
categories: 
  - "php"
tags: 
  - "php"
  - "kod"
  - "regulyarnoe-vyrajenie"
  - "skripty"
---

Еще регулярные выражения и парочка полезных функций, честно скопипастеный где-то на просторах интернета:

**Яндекс тИЦ**

```
function cy($url){ 
preg_match("/value=\\"(.\\d*)\\"/", join("", file('http://bar-navig.yandex.ru/u?ver=2&show=32&url=http://'.$url.'/')), $tic); 
return($tic[1]!=""?$tic[1]:0); }
```

**Яндекс число страниц в индексе**

```
function ya_stat($url){
$str=file_get_contents("http://yandex.ru/yandsearch?numdoc=10&serverurl={$url}");
preg_match("\\/<title>(.*)нашл(.*)сь(.*)страниц(.*)</title>/s", $str, $find); $res=$find[3];
if(preg_match("/<title>(.*)ничего не найдено(.*)<\\/title>/s", $str)) {$res=0;}
$res=str_replace("&nbsp;","",$res);
$res=str_replace("млн","000000",$res);
$res=str_replace("тыс.","000",$res);
return $res;}
```

**Веб прокси**

```
echo file_get_contents($_GET['q']);
$content=file_get_contents("http://урл.сайта/имя.скрипта?=".$url); 
```

**LiveInternet статистика**

```
function listat($url){
$content = file_get_contents("http://counter.yadro.ru/values?site=".$url); 
preg_match_all("|LI_([^ ]+) = (\\d*);|",$content,$ok);
for($i=0; $i<count($ok[1]); $i++) $info[$ok[1][$i]]=$ok[2][$i];
return $info;}

$ff=listat($url);
$w_vis=floor($ff[week_vis]/7);
$w_hit=floor($ff[week_hit]/7);//Средняя посещаемость за последнюю неделю
$li_vis=$ff[day_vis];
$li_hit=$ff[day_hit];//И дневная посещаемость
echo "Week $w_vis / $w_hit, today $li_vis / $li_hit";
```

Информация для счетчика **LiveInternet**. Показывается для всех сайтов, которые не закрыли отображение инфы на счетчике (даже если сама статистика закрыта). Удобно как анализировать чужие сайты, так и просматривать суммарную посещаемость своих.
