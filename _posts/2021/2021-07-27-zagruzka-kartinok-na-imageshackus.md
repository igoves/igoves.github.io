---
title: "Загрузка картинок на ImageShack.us"
categories: 
  - "php"
---

```
$filename = dirname(__FILE__) . '/image.jpg'; $postData = array(    'fileupload' => '@' . $filename,    'key'        => '*********', // ключ полученный на странице http://stream.imageshack.us/xmlapi/    'xml'        => 'yes',); $ch = curl_init('http://www.imageshack.us/upload_api.php');curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);curl_setopt($ch, CURLOPT_POST, 1);curl_setopt($ch, CURLOPT_POSTFIELDS, $postData);$result = curl_exec($ch);curl_close($ch); $xml = simplexml_load_string($result); if (!$xml){    echo 'Error';}else if (isset($xml->error)){    echo 'Error: ' . $xml->error;}else{    echo 'Image URL: ' . $xml->links->image_link;}
```
