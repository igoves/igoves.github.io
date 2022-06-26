---
title: "Вычислить возраст по дате рождения"
categories: 
  - "note"
---

```
SELECT  birthday,  (    (YEAR(CURRENT_DATE) - YEAR(birthday)) - /* step 1 */    (DATE_FORMAT(CURRENT_DATE, '%m%d') < DATE_FORMAT(birthday, '%m%d')) /* step 2 */  ) AS ageFROM users
```

  
birthday это поле с датой в любом валидном формате (не timestamp), например 1989-07-22 или даже 1989-07-22T00:00:00
