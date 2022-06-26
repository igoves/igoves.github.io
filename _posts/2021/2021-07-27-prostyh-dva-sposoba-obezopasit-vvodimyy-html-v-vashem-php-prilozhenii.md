---
title: "Простых два способа обезопасить вводимый HTML в вашем php приложении"
categories: 
  - "php"
---

Стандартными средствами

```
<?php
// Oh no!  The user has submitted malicious HTML, and we have to display it in our web app!
$evilHtml = '<div onclick="xss();">Mua-ha-ha!  Twiddling my evil mustache...</div>';

// Use the ENT_QUOTES flag to make sure both single and double quotes are escaped.
// Use the UTF-8 character encoding if you've stored the text as UTF-8 (as you should have).
// See the UTF-8 section in this document for more details.
$safeHtml = htmlentities($evilHtml, ENT_QUOTES, 'UTF-8'); // $safeHtml is now fully escaped HTML.  You can output $safeHtml to your users without fear!
?>
```

  
Или с использованием библиотеки HTMLPurifier

```

<?php
// Include the HTML Purifier library
require_once('htmlpurifier-4.6.0/HTMLPurifier.auto.php');
 
// Oh no!  The user has submitted malicious HTML, and we have to display it in our web app!
$evilHtml = '<div onclick="xss();">Mua-ha-ha!  Twiddling my evil mustache...</div>';
 
// Set up the HTML Purifier object with the default configuration.
$purifier = new HTMLPurifier(HTMLPurifier_Config::createDefault());
 
$safeHtml = $purifier->purify($evilHtml); // $safeHtml is now sanitized.  You can output $safeHtml to your users without fear!
?>
```
