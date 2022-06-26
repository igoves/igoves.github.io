---
title: "wapmorgan/Morphos - морфологическая библиотека, склоняет слова (русский и английский языки)"
date: ""
categories: 
  - "php"
---

```
// Inflect russian names:
morphos\\Russian\\inflectName('Иванов Петр', 'родительный') => 'Иванова Петра'

// Inflect geographical names:
morphos\\Russian\\GeographicalNamesInflection::getCase('Москва', 'родительный') => 'Москвы'

// Pluralize russian nouns:
morphos\\Russian\\pluralize(10, 'дом') => '10 домов'

// Generate russian cardinal numerals:
morphos\\Russian\\CardinalNumeralGenerator::getCase(567, 'именительный') => 'пятьсот шестьдесят семь'

// Generate russian ordinal numerals:
morphos\\Russian\\OrdinalNumeralGenerator::getCase(961, 'именительный') => 'девятьсот шестьдесят первый'
```

  
[https://github.com/wapmorgan/Morphos](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dhcG1vcmdhbi9Nb3JwaG9z)
