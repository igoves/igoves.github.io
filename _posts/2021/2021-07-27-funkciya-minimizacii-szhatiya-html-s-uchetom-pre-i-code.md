---
title: "Функция минимизации (сжатия) html с учетом pre и code"
categories: 
  - "php"
---

```
function htmlCompress($html) 
 {
    preg_match_all('!(<(?:code|pre).*>[^<]+</(?:code|pre)>)!',$html,$pre);
    $html = preg_replace('!<(?:code|pre).*>[^<]+</(?:code|pre)>!', '#.pre.#', $html);
    $html = preg_replace('#<!–[^\\[].+–>#', '', $html);
    $html = preg_replace('/[\\r\\n\\t]+/', ' ', $html);
    $html = preg_replace('/>[\\s]+</', '><', $html);
    $html = preg_replace('/[\\s]+/', ' ', $html);
    if (!empty($pre[0])) {
       foreach ($pre[0] as $tag) {
          $html = preg_replace('!#.pre.#!', $tag, $html,1);
       }
    }
    return $html;
 } 
```

Перед использованием в #.pre.# убрать точки. Эта функция ломает этот код, она используется здесь на сайте, поэтому добавил точки что бы ее отобразить =)
