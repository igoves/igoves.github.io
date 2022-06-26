---
title: "moment.php - аналог moment.js на php"
categories: 
  - "php"
---

  

```
$m = new \\Moment\\Moment(); // default is "now" UTC
echo $m->format(); // e.g. 2012-10-03T10:00:00+0000

$m = new \\Moment\\Moment('now', 'Europe/Berlin');
echo $m->format(); // e.g. 2012-10-03T12:00:00+0200

$m = new \\Moment\\Moment('2017-06-06T10:00:00', 'Europe/Berlin');
echo $m->format(); // e.g. 2012-10-03T12:00:00+0200

$m = new \\Moment\\Moment(1499366585);
echo $m->format(); // e.g. 2017-07-06T18:43:05+0000
```

  
[https://github.com/fightbulc/moment.php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2ZpZ2h0YnVsYy9tb21lbnQucGhw)
