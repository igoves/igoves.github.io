---
title: "terrylinooo/shieldon - защита от кучи запросов к сайту"
date: ""
categories: 
  - "php"
---

![terrylinooo/shieldon - защита от кучи запросов к сайту](https://camo.githubusercontent.com/3ac2116bb242e8d7b666f6d5563b611c35bc653c/68747470733a2f2f692e696d6775722e636f6d2f466647386654462e706e67 "terrylinooo/shieldon - защита от кучи запросов к сайту")

  
Когда пользователи или роботы пытаются просмотреть множество ваших веб-страниц за короткий промежуток времени, их временно банят. Получить разбан можно, пройдя капчу.  

```
$shieldon = new \\Shieldon\\Shieldon();

// Use SQLite as the data driver.
$dbLocation = APPPATH . 'cache/shieldon.sqlite3';
$pdoInstance = new \\PDO('sqlite:' . $dbLocation);
$shieldon->setDriver(new \\Shieldon\\Driver\\SqliteDriver($pdoInstance));

// Set components.
// This component will only allow popular search engine.
// Other bots will go into the checking process.
$shieldon->setComponent(new \\Shieldon\\Component\\TrustedBot());

// You can ignore this setting if you only use one Shieldon on your web application. This is for multiple instances.
$shieldon->setChannel('web_project');

// Only allow 10 sessions to view current page.
// The default expire time is 300 seconds.
$shieldon->limitSession(10);

// Set a Captcha servie. For example: Google recaptcha.
$shieldon->setCaptcha(new \\Shieldon\\Captcha\\Recaptcha([
    'key' => '6LfkOaUUAAAAAH-AlTz3hRQ25SK8kZKb2hDRSwz9',
    'secret' => '6LfkOaUUAAAAAJddZ6k-1j4hZC1rOqYZ9gLm0WQh',
]));

// Start protecting your website!

$result = $shieldon->run();


if ($result !== $shieldon::RESPONSE_ALLOW) {
    if ($shieldon->captchaResponse()) {

        // Unban current session.
        $shieldon->unban();
    }
    // Output the result page with HTTP status code 200.
    $shieldon->output(200);
}
```

  
[https://github.com/terrylinooo/shieldon](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3RlcnJ5bGlub29vL3NoaWVsZG9u)
