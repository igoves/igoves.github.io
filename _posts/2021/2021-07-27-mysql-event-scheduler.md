---
title: "MySQL Event Scheduler"
categories: 
  - "note"
tags: 
  - "event"
  - "mysql"
  - "scheduler"
---

![MySQL Event Scheduler](images/1356861213_2.jpg "MySQL Event Scheduler")

  
  
2) Создаем Event-ы  

```
CREATE EVENT antibrutON SCHEDULE EVERY 1 HOURDODELETE FROM _antibrut WHERE logintime < DATE_SUB(NOW(),INTERVAL 1 HOUR)
```

  

```
CREATE EVENT antispamON SCHEDULE EVERY 1 HOURDODELETE FROM _antispam WHERE time < DATE_SUB(NOW(),INTERVAL 1 HOUR)
```

  
  
**Дополнительно**  
**Посмотреть Event-ы**:  

```
SHOW EVENTS;
```

  
  
Если хотить **модифицирывать ваш Event**, делать через ALTER, например:  

```
ALTER antibrut ON SCHEDULE EVERY 5 HOUR STARTS TIMESTAMP + 3 HOUR 
```

  
  
**Удалить Event:**  

```
DROP EVENT antispam;
```
