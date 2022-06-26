---
title: "soluble-mediatools - php обертка для video conversions, transcoding, querying, thumbnailing, wraps around ffmpeg and ffprobe"
categories: 
  - "php"
---

```
<?php
use Soluble\\MediaTools\\Video\\Config\\FFProbeConfig;
use Soluble\\MediaTools\\Video\\Exception\\InfoReaderExceptionInterface;
use Soluble\\MediaTools\\Video\\VideoInfoReader;

$infoReader = new VideoInfoReader(new FFProbeConfig('/path/to/ffprobe'));

try {
    $videoInfo = $infoReader->getInfo('/path/video.mp4');
} catch (InfoReaderExceptionInterface $e) {
    // see below for exceptions
}

$duration = $videoInfo->getDuration();
$frames   = $videoInfo->getNbFrames();
$width    = $videoInfo->getWidth();
$height   = $videoInfo->getHeight();

// Or alternatively
['width' => $width, 'height' => $height] = $videoInfo->getDimensions();
       
```

  
[https://github.com/soluble-io/soluble-mediatools/](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NvbHVibGUtaW8vc29sdWJsZS1tZWRpYXRvb2xzLw%3D%3D)
