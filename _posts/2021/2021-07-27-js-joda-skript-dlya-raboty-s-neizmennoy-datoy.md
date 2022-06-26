---
title: "js-joda - скрипт для работы с неизменной датой"
categories: 
  - "js"
---

Пример

```
// obtain the current date in the system default timezone, e.g. 2016-02-23
LocalDate.now();

// obtain the current date in the utc timezone, e.g. 2016-02-23
LocalDate.now(ZoneOffset.UTC);

// obtain an instance of LocalDate from an ISO8601 formatted text string
LocalDate.parse('2016-02-23');

// obtain an instance of LocalDate from a year, month, and dayOfMonth value
LocalDate.of(2016, 2, 23) // 2016-02-23

// obtain an instance of LocalDate from a year, month, and dayOfMonth value
LocalDate.of(2016, Month.FEBRUARY, 23) // 2016-02-23

// obtain an instance of LocalDate from am epochDay where day 0 is 1970-01-01
LocalDate.ofEpochDay(-1) // 1969-12-31

// obtain an instance of LocalDate from am epochDay where day 0 is 1970-01-01
LocalDate.ofYearDay(2016, 42) // 2016-02-11
```

  
[https://js-joda.github.io/js-joda/](https://dev.xfor.top/go/aHR0cHM6Ly9qcy1qb2RhLmdpdGh1Yi5pby9qcy1qb2RhLw%3D%3D)
