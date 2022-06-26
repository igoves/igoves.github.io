---
title: "EmailReplyParser - php библиотека для распарсивания простых текстовых писем"
categories: 
  - "php"
---

Пример

```
<?php

use EmailReplyParser\\Parser\\EmailParser;

$email = (new EmailParser())->parse($emailContent);
$fragment = current($email->getFragments());

$fragment->getContent();

$fragment->isSignature();

$fragment->isQuoted();

$fragment->isHidden();

$fragment->isEmpty();
$email = \\EmailReplyParser\\EmailReplyParser::read($emailContent);

$visibleText = \\EmailReplyParser\\EmailReplyParser::parseReply($emailContent);
```

  
[https://github.com/willdurand/EmailReplyParser](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dpbGxkdXJhbmQvRW1haWxSZXBseVBhcnNlcg%3D%3D)
