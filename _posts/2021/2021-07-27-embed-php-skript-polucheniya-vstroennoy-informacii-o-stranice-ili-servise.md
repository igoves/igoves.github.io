---
title: "Embed - php скрипт получения встроенной информации о странице или сервисе"
categories: 
  - "php"
---

Скрипт использует oembed, opengraph, twitter-cards, scrapping the html и др. Совместимый с любым веб-сервисом (youtube, vimeo, flickr, instagram, etc) и имеет адаптеры для сайтов типа (archive.org, github, facebook, etc).  
  
**Требования**: PHP 5.4+, Curl library installed  
  
**Пример использования с ютубом**

```
//Load library (if you don't have composer or any psr-4 compatible loader):
include('src/autoloader.php');

//Load any url:
$info = Embed\\Embed::create('https://www.youtube.com/watch?v=PP1xn5wHtxE');

//Get content info

$info->title; //The page title
$info->description; //The page description
$info->url; //The canonical url
$info->type; //The page type (link, video, image, rich)

$info->images; //List of all images found in the page
$info->image; //The image choosen as main image
$info->imageWidth; //The width of the main image
$info->imageHeight; //The height of the main image

$info->code; //The code to embed the image, video, etc
$info->width; //The width of the embed code
$info->height; //The height of the embed code
$info->aspectRatio; //The aspect ratio (width/height)

$info->authorName; //The (video/article/image/whatever) author 
$info->authorUrl; //The author url

$info->providerName; //The provider name of the page (youtube, twitter, instagram, etc)
$info->providerUrl; //The provider url
$info->providerIcons; //All provider icons found in the page
$info->providerIcon; //The icon choosen as main icon

$info->publishedDate; //The (video/article/image/whatever) published date
```
