---
title: "parpalak/rose - простой полнотекстовый поисковый движек на php с поддержкой русской морфологии"
categories: 
  - "php"
---

```
use S2\\Rose\\Finder;
use S2\\Rose\\Entity\\Query;

$finder = new Finder($storage, $stemmer);
$resultSet = $finder->find(new Query('content'));

foreach ($resultSet->getItems() as $externalId => $item) {
	                         // first iteration:          second iteration:
	$externalId;             // 'id_2'                    'id_1'
	$item->getTitle();       // 'Test page title 2'       'Test page title'
	$item->getUrl();         // ''                        'url1'
	$item->getDescription(); // ''                        'Description can be used in snippets'
	$item->getDate();        // null                      new \\DateTime('2016-08-24 00:00:00')
	$item->getRelevance();   // 31.0                      1.0
	$item->getSnippet();     // ''                        'Description can be used in snippets'
}
```

  
[https://github.com/parpalak/rose](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BhcnBhbGFrL3Jvc2U%3D)
