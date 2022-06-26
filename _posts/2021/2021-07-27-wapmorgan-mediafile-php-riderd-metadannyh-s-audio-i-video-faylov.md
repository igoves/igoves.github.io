---
title: "wapmorgan/MediaFile - php ридерд метаданных с аудио и видео файлов"
date: ""
categories: 
  - "php"
---

```
try {
  $media = wapmorgan\\MediaFile\\MediaFile::open('123.mp3');
  // for audio
  if ($media->isAudio()) {
    // calls to AudioAdapter interface
    echo 'Duration: '.$media->getAudio()->getLength().PHP_EOL;
    echo 'Bit rate: '.$media->getAudio()->getBitRate().PHP_EOL;
    echo 'Sample rate: '.$media->getAudio()->getSampleRate().PHP_EOL;
    echo 'Channels: '.$media->getAudio()->getChannels().PHP_EOL;
  }
  // for video
  else {
    // calls to VideoAdapter interface
    echo 'Duration: '.$media->getVideo()->getLength().PHP_EOL;
    echo 'Dimensions: '.$media->getVideo()->getWidth().'x'.$media->getVideo()->getHeight().PHP_EOL;
    echo 'Framerate: '.$media->getVideo()->getFramerate().PHP_EOL;
  }
} catch (wapmorgan\\MediaFile\\Exception $e) {
  // not a media or file is corrupted
  if ($e instanceof wapmorgan\\MediaFile\\FileAccessException)
      echo 'File '.$file.' is not a media file'.PHP_EOL;
  else {
      echo 'File is propably corrupted: '.$e->getMessage().PHP_EOL;
  }
}
```

  
[https://github.com/wapmorgan/MediaFile](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dhcG1vcmdhbi9NZWRpYUZpbGU%3D)
