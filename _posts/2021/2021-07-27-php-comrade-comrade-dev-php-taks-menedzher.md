---
title: "php-comrade/comrade-dev - php такс менеджер"
date: ""
categories: 
  - "php"
---

Поддерживает любой сервер очередей, создание таска  

```
$template = JobTemplate::create();
$template->setName('demo_success_job');
$template->setTemplateId(Uuid::generate());
$template->setRunner(QueueRunner::createFor('demo_success_job'));

$policy = GracePeriodPolicy::create();
$policy->setPeriod(20);
$template->setGracePeriodPolicy($policy);

$trigger = CronTrigger::create();
$trigger->setTemplateId($template->getTemplateId());
$trigger->setStartAt(new \\DateTime('now'));
$trigger->setMisfireInstruction(CronTrigger::MISFIRE_INSTRUCTION_FIRE_ONCE_NOW);
$trigger->setExpression('*/5 * * * *');

$createJob = CreateJob::createFor($template);
$createJob->addTrigger($trigger);

$queue = $context->createQueue('comrade_create_job');
$message = $context->createMessage(JSON::encode($createJob));
$context->createProducer()->send($queue, $message);
```

  
[https://github.com/php-comrade/comrade-dev](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BocC1jb21yYWRlL2NvbXJhZGUtZGV2)
