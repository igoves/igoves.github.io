---
title: "anti-csrf - библиотека анти-CSRF"
categories: 
  - "php"
---

Защита основана на сессиях, использует SPL autoloader  
Добавляете фильтр (используя Twig templates)

```
use \\ParagonIE\\AntiCSRF\\AntiCSRF;
$twigEnv->addFunction(
    new \\Twig_SimpleFunction(
        'form_token',
        function($lock_to = null) {
            return AntiCSRF::insertToken($lock_to, false);
        },
        ['is_safe' => ['html']]
    )
);
```

  
Встраиваете в форму

```
<form action="/addUser.php" method="post">
    {{ form_token("/addUser.php") }}

    {# ... the rest of your form here ... #}
</form>
```

  
Проверяете валидность

```
    if (!empty($_POST)) {
        if (\\ParagonIE\\AntiCSRF\\AntiCSRF::validateRequest()) {
            // Valid
        } else {
            // Log a CSRF attack attempt
        }
    }
```

  
[https://github.com/paragonie/anti-csrf](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BhcmFnb25pZS9hbnRpLWNzcmY%3D)
