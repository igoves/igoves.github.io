---
title: "heyupdate/Emoji - эмодзи из символов и имен Unicode на PHP"
date: "2021-02-13"
categories: 
  - "php"
---

```
use HeyUpdate\Emoji\Emoji;
use HeyUpdate\Emoji\EmojiIndex;

$emoji = new Emoji(new EmojiIndex(), '//twemoji.maxcdn.com/36x36/%s.png');
$emoji->replaceEmojiWithImages('🎈 :balloon:');
```

[https://github.com/heyupdate/Emoji](https://github.com/heyupdate/Emoji)
