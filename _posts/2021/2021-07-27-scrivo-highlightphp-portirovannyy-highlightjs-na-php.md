---
title: "scrivo/highlight.php - портированный highlight.js на php"
categories: 
  - "php"
---

```
$hl = new Highlight\\Highlighter();
$hl->setAutodetectLanguages(array('ruby', 'python', 'perl'));

$highlighted = $hl->highlightAuto(file_get_contents('some_ruby_script.rb'));

echo "<pre class=\\"hljs {$highlighted->language}\\">\\n";
echo $highlighted->value . "\\n";
echo "</pre>\\n";
```

  
[https://github.com/scrivo/highlight.php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Njcml2by9oaWdobGlnaHQucGhw)
