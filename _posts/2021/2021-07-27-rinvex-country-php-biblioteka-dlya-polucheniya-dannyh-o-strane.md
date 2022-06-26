---
title: "rinvex/country - php библиотека для получения данных о стране"
categories: 
  - "php"
---

```
// Get single country
$egypt = country('eg');

// Get country name                                 // Get country native name
echo $egypt->getName();                             echo $egypt->getNativeName();

// Get country official name                        // Get country ISO 3166-1 alpha2 code
echo $egypt->getOfficialName();                     echo $egypt->getIsoAlpha2();

// Get country area                                 // Get country borders
echo $egypt->getArea();                             echo $egypt->getBorders();

// Get country currencies                           // Get country languages
echo $egypt->getCurrencies();                       echo $egypt->getLanguages();

// Get country emoji                                // Get country flag
echo $egypt->getEmoji();                            echo $egypt->getFlag();


// Get all countries                                // Get countries with where condition (continent: Oceania)
$countries = countries();                           $whereCountries = \\Rinvex\\Country\\Loader::where('geo.continent', ['OC' => 'Oceania']);
```

  
[https://github.com/rinvex/country](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3JpbnZleC9jb3VudHJ5)
