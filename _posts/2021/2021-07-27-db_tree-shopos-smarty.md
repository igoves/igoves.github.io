---
title: "Список товаров в категории ShopOS"
categories: 
  - "php"
tags: 
  - "db_tree"
  - "mysql"
  - "shopos"
  - "smarty"
---

![Список товаров в категории ShopOS](images/1307447639_pic3.jpg "Список товаров в категории ShopOS")

  
Теперь, когда вы нажимаете на подкатегорию выпадает еще и список товаров. Оптимизируйте и ковыряйте -) Да и не забудьте в коде поменять префикс БД на свой.  
  
**UPD 02.09.11. для еще одного уровня + оптимизирован код.**  
вставить в оригинальный файл show\_category.inc.php после ( $foo\[$cid\]\[\\'name\\'\].$ProductsCount. \\'\\'; - 114 строчка)  

```
                        if ($level == 3) {                            if ( !empty($Aktiv)) {                                //$categories_string .= $cid;                                $query = "SELECT * FROM                                     vip_products_to_categories p2c,                                    vip_products p,                                    vip_products_description pd                                WHERE                                     p2c.categories_id = '".$cid."'                                    and p.products_status = '1'                                     and p.products_id = p2c.products_id                                     and p.products_id=pd.products_id                                ORDER by p.products_date_added";                                $query = osDBquery($query);                                $categories_string .= "<ul>";                                while ($row1 = os_db_fetch_array($query)) {                                     $categories_string .= "<li />[url=/product_info.php?products_id={$row1[]".$row1['products_name']."[/url]";                                }                                      $categories_string .= "</ul>";                            }                        }
```
