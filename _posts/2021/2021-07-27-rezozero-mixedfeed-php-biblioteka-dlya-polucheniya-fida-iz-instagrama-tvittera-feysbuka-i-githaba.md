---
title: "rezozero/mixedfeed - php библиотека для получения фида из инстаграма, твиттера, фейсбука и гитхаба"
date: ""
categories: 
  - "php"
---

```
use RZ\\MixedFeed\\MixedFeed;
use RZ\\MixedFeed\\InstagramFeed;
use RZ\\MixedFeed\\TwitterFeed;
use RZ\\MixedFeed\\TwitterSearchFeed;
use RZ\\MixedFeed\\FacebookPageFeed;
use RZ\\MixedFeed\\GithubReleasesFeed;
use RZ\\MixedFeed\\GithubCommitsFeed;

$feed = new MixedFeed([
    new InstagramFeed(
        'instagram_user_id',
        'instagram_access_token',
        null // you can add a doctrine cache provider
    ),
    new TwitterFeed(
        'twitter_user_id',
        'twitter_consumer_key',
        'twitter_consumer_secret',
        'twitter_access_token',
        'twitter_access_token_secret',
        null,  // you can add a doctrine cache provider
        true,  // exclude replies true/false
        false, // include retweets true/false
        false  // extended mode true/false
    ),
    new TwitterSearchFeed(
        [
            '#art', // do not specify a key for string searchs
            'from' => 'rezo_zero',
            'since' => '2015-11-01',
            'until' => '2015-11-30',
        ],
        'twitter_consumer_key',
        'twitter_consumer_secret',
        'twitter_access_token',
        'twitter_access_token_secret',
        null,  // you can add a doctrine cache provider
        false  // extended mode true/false
    ),
    new FacebookPageFeed(
        'page-id',
        'app_access_token',
        null, // you can add a doctrine cache provider
        []    // And a fields array to retrieve too
    ),
    new GithubCommitsFeed(
        'symfony/symfony',
        'access_token',
        null // you can add a doctrine cache provider
    ),
    new GithubReleasesFeed(
        'roadiz/roadiz',
        'access_token',
        null // you can add a doctrine cache provider
    ),
]);

return $feed->getItems(12);
```

  
[https://github.com/rezozero/mixedfeed](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Jlem96ZXJvL21peGVkZmVlZA%3D%3D)
