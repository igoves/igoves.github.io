---
title: "Faker - php библиотека для создания фейковых данных"
date: ""
categories: 
  - "php"
---

В продолжении вчерашнему посту о создании фейковых данных. Встречайте **Faker**  
Сразу пример использования:

```
<?php
// require the Faker autoloader
require_once '/path/to/Faker/src/autoload.php';
// alternatively, use another PSR-0 compliant autoloader (like the Symfony2 ClassLoader for instance)

// use the factory to create a Faker\\Generator instance
$faker = Faker\\Factory::create();

// generate data by accessing properties
echo $faker->name;
  // 'Lucy Cechtelar';
echo $faker->address;
  // "426 Jordy Lodge
  // Cartwrightshire, SC 88120-6700"
echo $faker->text;
  // Sint velit eveniet. Rerum atque repellat voluptatem quia rerum. Numquam excepturi
  // beatae sint laudantium consequatur. Magni occaecati itaque sint et sit tempore. Nesciunt
  // amet quidem. Iusto deleniti cum autem ad quia aperiam.
  // A consectetur quos aliquam. In iste aliquid et aut similique suscipit. Consequatur qui
  // quaerat iste minus hic expedita. Consequuntur error magni et laboriosam. Aut aspernatur
  // voluptatem sit aliquam. Dolores voluptatum est.
  // Aut molestias et maxime. Fugit autem facilis quos vero. Eius quibusdam possimus est.
  // Ea quaerat et quisquam. Deleniti sunt quam. Adipisci consequatur id in occaecati.
  // Et sint et. Ut ducimus quod nemo ab voluptatum.
```

  
Может генерировать адреса, телефоны, компании, даты, цвета, методы оплаты, файлы, картинки, юзерагенты и многое другое.  
[https://github.com/fzaninotto/Faker](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2Z6YW5pbm90dG8vRmFrZXI%3D)
