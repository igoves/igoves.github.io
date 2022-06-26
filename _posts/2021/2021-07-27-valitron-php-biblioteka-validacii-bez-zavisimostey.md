---
title: "valitron - php библиотека валидации без зависимостей"
categories: 
  - "php"
---

Пример

```
$v = new Valitron\\Validator(array('name' => 'Chester Tester'));
$v->rule('required', 'name');
if($v->validate()) {
    echo "Yay! We're all good!";
} else {
    // Errors
    print_r($v->errors());
}
```

  
[https://github.com/vlucas/valitron](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3ZsdWNhcy92YWxpdHJvbg%3D%3D)
