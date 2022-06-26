---
title: "Полезные функции PHP"
date: ""
categories: 
  - "php"
tags: 
  - "zametki"
  - "funkcii"
  - "chernovik"
---

![Полезные функции PHP](images/1294339977_72.jpg "Полезные функции PHP")

  
**Простой способ реализации списка структуры папок**  

```
$path = "/home/user/public/foldername/";$dir_handle = @opendir($path) or die("Unable to open $path");while ($file = readdir($dir_handle)) {    if($file == "." || $file == ".." || $file == "index.php" )        continue;        echo "<a href=\\"$file\\">$file</a><br />";    }closedir($dir_handle);
```

  
  
**Создание защищенной паролем страницы**  

```
<?$username = "someuser";$password = "somepassword";if ($_POST['txtUsername'] != $username || $_POST['txtPassword'] != $password) {?><h1>Login</h1><form name="form" method="post" action="<?php echo $_SERVER['PHP_SELF']; ?>">      <p><label for="txtUsername">Username:</label>      <br><input type="text" title="Enter your Username" name="txtUsername"></p>      <p><label for="txtpassword">Password:</label>      <br><input type="password" title="Enter your password" name="txtPassword"></p>  <p><input type="submit" name="Submit" value="Login"></p></form><?} else {?>    <p>This is the protected page. Your private content goes here.</p><?}?>
```

  
  
**Искать файлы, используя шаблоны**  

```
$files = glob('*.php');print_r($files);/* Выдаст что-то типа:Array(    [0] => phptest.php    [1] => pi.php    [2] => post_output.php    [3] => test.php)*/
```

  
  
**Сериализация**  

```
// a complex array$myvar = array(    'hello',    42,    array(1,'two'),    'apple');// convert to a string$string = serialize($myvar);echo $string;/* printsa:4:{i:0;s:5:"hello";i:1;i:42;i:2;a:2:{i:0;i:1;i:1;s:3:"two";}i:3;s:5:"apple";}*/// you can reproduce the original variable$newvar = unserialize($string);print_r($newvar);/* printsArray(    [0] => hello    [1] => 42    [2] => Array        (            [0] => 1            [1] => two        )    [3] => apple)*/
```
