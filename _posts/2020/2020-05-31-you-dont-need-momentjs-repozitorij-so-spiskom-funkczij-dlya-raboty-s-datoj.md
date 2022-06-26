---
title: "You-Dont-Need-Momentjs - репозиторий со списком функций для работы с датой"
date: "2020-05-31"
categories: 
  - "js"
tags: 
  - "date"
  - "momentjs"
---

Список функций который может заменить библиотеку довольно тяжелую (по производительности) библиотеку moment.js

![](images/screenshot.png)

```
// Moment.js
moment('12-25-1995', 'MM-DD-YYYY');
// => "1995-12-24T13:00:00.000Z"

// Native
const datePattern = /^(\d{2})-(\d{2})-(\d{4})$/;
const [, month, day, year] = datePattern.exec('12-25-1995');
new Date(`${month}, ${day} ${year}`);
// => "1995-12-24T13:00:00.000Z"

// date-fns
import parse from 'date-fns/parse';
parse('12-25-1995', 'MM-dd-yyyy', new Date());
// => "1995-12-24T13:00:00.000Z"

// dayjs
dayjs('12-25-1995');
// => "1995-12-24T13:00:00.000Z"

// luxon
DateTime.fromFormat('12-25-1995', 'MM-dd-yyyy').toJSDate();
// => "1995-12-24T13:00:00.000Z"
```

[https://github.com/you-dont-need/You-Dont-Need-Momentjs](https://github.com/you-dont-need/You-Dont-Need-Momentjs)
