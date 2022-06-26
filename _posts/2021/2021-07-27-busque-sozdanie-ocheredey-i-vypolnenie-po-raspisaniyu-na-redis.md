---
title: "BusQue - создание очередей и выполнение по расписанию на Redis"
date: ""
categories: 
  - "php"
---

Поставить в очередь

```
<?php

$command = new SendEmailCommand('joe@example.com', 'Hello Joe!');

$commandBus->handle(new BusQue\\QueuedCommand($command));

// or

$busQue->queueCommand($command);
```

  
Выполнение

```
<?php

$busQue->workQueue('default'); // Hello Joe!
```

  
Выполнение по расписанию в очередь ставим

```
<?php

$commandBus->handle(new BusQue\\ScheduledCommand($command, new \\DateTime('+1 minute')));

// or

$busQue->scheduleCommand($command, new \\DateTime('+1 minute'));
```

  
[https://github.com/mgdigital/busque](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21nZGlnaXRhbC9idXNxdWU%3D)
