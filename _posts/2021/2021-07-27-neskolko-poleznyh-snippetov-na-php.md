---
title: "Несколько полезных сниппетов на php"
categories: 
  - "php"
---

**Удалить двойные пробелы PHP**  

```
<?php$str = 'Но    чтобы    вы  поняли,  откуда   возникает    это   превратное    представление    людей,<br>порицающих   наслаждение  и   восхваляющих   страдания,   я   раскрою    перед   вами  всю    картину<br>и   разъясню,  что   именно   говорил   этот   человек,   открывший    истину,  которого я  бы назвал<br>зодчим   счастливой     жизни.';$fixed_str = preg_replace('/[\\s]{2,}/', ' ', $str);/** РезультатНо чтобы вы поняли, откуда возникает это превратное представление людей,<br>порицающих наслаждение и восхваляющих страдания, я раскрою перед вами всю картину<br>и разъясню, что именно говорил этот человек, открывший истину, которого я бы назвал<br>зодчим счастливой жизни.*/?>
```

  
**Вырезать все кроме цифр PHP**  

```
<?php$str = 'But I must 123 explain to you 345 how all this 2 mistaken idea of denouncingpleasu645re and praising pa84in was born and I will give 6you a complete acco87untof the system, and 098 expound the actual teachings of the gr42eat explorer of the truth,the maste64r-bu88ilder of human happi24ness.';echo preg_replace('/[^0-9]/', '', $str); // 12334526458468709842648824?>
```

  
**Сделать первую букву заглавной PHP**  
Английские буквы и Кириллица Windows-1251  
С английскими буквами в стандартно-используемых кодировках (UTF-8 и Windows-1251) проблем не возникает.  

```
<?php// строка$str = 'first letters';// первая буква в верхний регистрecho ucfirst($str) . '<br>';// первая буква во всех словахecho ucwords($str);?>
```

  
**Кириллица и UTF-8**  

```
<?php/** * проверяем, что функция mb_ucfirst не объявлена * и включено расширение mbstring (Multibyte String Functions) */if (!function_exists('mb_ucfirst') && extension_loaded('mbstring')){    /**     * mb_ucfirst - преобразует первый символ в верхний регистр     * @param string $str - строка     * @param string $encoding - кодировка, по-умолчанию UTF-8     * @return string     */    function mb_ucfirst($str, $encoding='UTF-8')    {        $str = mb_ereg_replace('^[\\ ]+', '', $str);        $str = mb_strtoupper(mb_substr($str, 0, 1, $encoding), $encoding).               mb_substr($str, 1, mb_strlen($str), $encoding);        return $str;    }}$str = 'первые буквы';// пробуем кириллицу в юникоде преобразовать функцией ucfirstecho ucfirst($str) . '<br>';// пробуем кириллицу в юникоде преобразовать функцией ucwordsecho ucwords($str) . '<br>';// обрабатываем объявленной функцией mb_ucfirst()echo mb_ucfirst($str) . '<br>';// преобразовываем функцией mb_convert_caseecho mb_convert_case($str, MB_CASE_TITLE, 'UTF-8');?>
```

  
**Результат** с утф-кодировкой преобразований  
первые буквы  
первые буквы  
Первые буквы  
Первые Буквы
