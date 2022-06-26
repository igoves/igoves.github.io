---
title: "PHP ORM для Redis"
categories: 
  - "php"
---

Пример  
Создание связи адреса с юзером

```
$address = new Address();
$address->setId(1)->setStreet("123 Example St");

$user = new User();
$user->setId(1)->setName("Harry")->setAddress($address);

$em->persist($user)->persist($address)->flush();
```

  
Получение адреса юзера

```
$user = $em->retrieve('User', 1);   // Only user entity retrieved
$address = $user->getAddress();     // DB call to get address made here
```

  
[https://github.com/bravo3/orm](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2JyYXZvMy9vcm0%3D)
