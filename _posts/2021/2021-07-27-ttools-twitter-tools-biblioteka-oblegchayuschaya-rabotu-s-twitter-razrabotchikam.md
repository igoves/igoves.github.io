---
title: "TTools (Twitter Tools) - библиотека облегчающая работу с twitter разработчикам"
date: ""
categories: 
  - "php"
---

Пример: авторизация и получения username и его timeline  

```
$config = array(    'consumer_key'    => 'APP_CONSUMER_KEY',    'consumer_secret' => 'APP_CONSUMER_SECRET');$app = new \\TTools\\App($config);if ($app->isLogged()) {    $user = $app->getCurrentUser();    echo "<h3>Logged in as @". $user['screen_name'] . "</h3>";    echo '<p>[ <a href=".?logout=1">Logout</a> ]';    $tl = $app->getTimeline();    echo "<h3>Your Timeline</h3><pre>";    print_r($tl);    echo "</pre>";    echo "Last Req Info:<br/>";    print_r($app->getLastReqInfo());} else {    $login_url = $app->getLoginUrl();    echo 'Please log in: <a href="'. $login_url . '">' . $login_url . '</a>';}
```

  
[http://ttools.github.io/ttools/](https://dev.xfor.top/go/aHR0cDovL3R0b29scy5naXRodWIuaW8vdHRvb2xzLw%3D%3D)
