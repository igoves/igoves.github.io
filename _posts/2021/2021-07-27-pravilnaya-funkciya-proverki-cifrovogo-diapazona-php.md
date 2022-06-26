---
title: "Правильная функция проверки цифрового диапазона PHP"
date: ""
categories: 
  - "php"
---

```
function checkIntegerRange($int, $min, $max)
{
    if (is_string($int) && !ctype_digit($int)) {
        return false; // contains non digit characters
    }
    if (!is_int((int) $int)) {
        return false; // other non-integer value or exceeds PHP_MAX_INT
    }
    return ($int >= $min && $int <= $max);
}
```
