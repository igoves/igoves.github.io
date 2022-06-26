---
title: "remotelyliving/php-dns - DNS абстракция в PHP"
categories: 
  - "php"
---

```
$resolver = new Resolvers\\GoogleDNS();
$hostname = 'google.com';

// can query via convenience methods
$records = $resolver->getARecords($hostname); // returns a collection of DNS A Records

// can also query by any RecordType. Record Types are a proper object that validate you have the right type.
$recordType = DNSRecordType::createAAAA();

// OR

$recordType = DNSRecordType::TYPE_AAAA;

$moreRecords = $resolver->getRecords($hostname, $recordType);

// can query to see if any resolvers find a record or type.
$resolver->hasRecordType($hostname, $type) // true | false
$resolver->hasRecord($record) // true | false

// This becomes very powerful when used with the Chain Resolver
```

  
[https://github.com/remotelyliving/php-dns](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3JlbW90ZWx5bGl2aW5nL3BocC1kbnM%3D)
