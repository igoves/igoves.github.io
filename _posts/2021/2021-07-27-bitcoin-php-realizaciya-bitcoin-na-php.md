---
title: "bitcoin-php - реализация bitcoin на php"
categories: 
  - "php"
---

Пример кода

```
use BitWasp\\Buffertools\\Buffer;
use BitWasp\\Bitcoin\\Transaction\\OutPoint;
use BitWasp\\Bitcoin\\Script\\Script;
use BitWasp\\Bitcoin\\Transaction\\TransactionInput;

$txid = Buffer::hex('87f7b7639d132e9817f58d3fe3f9f65ff317dc780107a6c10cba5ce2ad1e4ea1');
$vout = 0;
$outpoint = new OutPoint($txid, $vout);

$sequence = TransactionInput::SEQUENCE_FINAL;
$script = new Script();
$input = new TransactionInput($outpoint, $script, $sequence);
```

[https://github.com/bit-wasp/bitcoin-php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2JpdC13YXNwL2JpdGNvaW4tcGhw)
