---
title: "ipgeobase-importer - импортер ipgeobase базы русских городов в файлы"
date: ""
categories: 
  - "note"
---

Импортер ipgeobase базы русских городов в файлы, понятные для nginx geoip module, с поддержкой кодов регионов РФ.  
  
Скачивает geo\_files.zip с сайта ipgeobase.ru  
Конвертирует базу в два файла:  
city.txt, вида: - base64();  
region.txt, вида: - ; (01-99)  
Скачивает списки TOR с torproject и blutmagie.de  
Создает tor.txt, вида: - 1;  
  
[https://github.com/m-messiah/ipgeobase-importer](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL20tbWVzc2lhaC9pcGdlb2Jhc2UtaW1wb3J0ZXI%3D)
