---
title: "hutnikau/job-scheduler - планировщик задач на пхп"
date: ""
categories: 
  - "js"
---

```
$executionTime = new \\DateTime('2017-12-12 20:00:00');
//run monthly, at 20:00:00, 5 times
$rule          = new \\Scheduler\\Job\\RRule('FREQ=MONTHLY;COUNT=5', $executionTime);
$job           = new \\Scheduler\\Job\\Job($rule, function () {
    //do something
});
```

  
[https://github.com/hutnikau/job-scheduler](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2h1dG5pa2F1L2pvYi1zY2hlZHVsZXI%3D)
