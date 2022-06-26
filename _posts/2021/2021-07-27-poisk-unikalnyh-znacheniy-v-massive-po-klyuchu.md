---
title: "Поиск уникальных значений в массиве по ключу"
categories: 
  - "php"
---

```
 function remove_dups($array, $row_element) {     $new_array[0] = $array[0];     foreach ($array as $current) {         $add_flag = 1;         foreach ($new_array as $tmp) {             if ($current[$row_element]==$tmp[$row_element]) {                 $add_flag = 0; break;             }         }         if ($add_flag) $new_array[] = $current;     }     return $new_array; }
```

  
  
Имеем массив:  
2012 - январь  
2012 - февраль  
2012 - январь  
  
Сортируем его по ключу month  

```
$array2 = remove_dups($array, 'month');
```

  
  
Результат выполнения:  
2012 - январь  
2012 - февраль
