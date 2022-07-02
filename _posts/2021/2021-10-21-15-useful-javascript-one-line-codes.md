---
title: "15 useful  Javascript one line codes"
date: "2021-10-21"
categories: 
  - "js"
tags: 
  - "helpfull"
  - "oneline"
  - "snippets"
---

**Get Value of a brower Cookie**

```
const cookie = name => `; ${document.cookie}`.split(`; ${name}=`).pop().split(';').shift();

cookie('_ga');
// Result: "GA1.2.1929736587.1601974046"
```

**Copy to Clipboard**

```
const copyToClipboard = (text) => navigator.clipboard.writeText(text);

copyToClipboard("Hello World");
```

**Check if Date is Valid**

```
const isDateValid = (...val) => !Number.isNaN(new Date(...val).valueOf());

isDateValid("December 17, 1995 03:24:00");
// Result: true
```

**Find the day of year**

```
const dayOfYear = (date) =>
  Math.floor((date - new Date(date.getFullYear(), 0, 0)) / 1000 / 60 / 60 / 24);

dayOfYear(new Date());
// Result: 272
```

**Capitalise a String**

```
const capitalize = str => str.charAt(0).toUpperCase() + str.slice(1)

capitalize("follow for more")
// Result: Follow for more
```

**Find the number of days between two days**

```
const dayDif = (date1, date2) => Math.ceil(Math.abs(date1.getTime() - date2.getTime()) / 86400000)

dayDif(new Date("2020-10-21"), new Date("2021-10-22"))
// Result: 366
```

**Clear All Cookies**

```
const clearCookies = document.cookie.split(';').forEach(cookie => document.cookie = cookie.replace(/^ +/, '').replace(/=.*/, `=;expires=${new Date(0).toUTCString()};path=/`));
```

**Remove Duplicated from Array**

```
const removeDuplicates = (arr) => [...new Set(arr)];

console.log(removeDuplicates([1, 2, 3, 3, 4, 4, 5, 5, 6]));
// Result: [ 1, 2, 3, 4, 5, 6 ]
```

**Get Query Params from URL**

```
const getParameters = (URL) => {
  URL = JSON.parse('{"' + decodeURI(URL.split("?")[1]).replace(/"/g, '\\"').replace(/&/g, '","').replace(/=/g, '":"') +'"}');
  return JSON.stringify(URL);
};

getParameters(window.location)
// Result: { search : "easy", page : 3 }
```

**Check if a number is even or odd**

```
const isEven = num => num % 2 === 0;

console.log(isEven(2)); 
// Result: True
```

**Find Average of Numbers**

```
const average = (...args) => args.reduce((a, b) => a + b) / args.length;

average(1, 2, 3, 4);
// Result: 2.5
```

**Scroll to Top**

```
const goToTop = () => window.scrollTo(0, 0);

goToTop();
```

**Check if array is empty**

```
const isNotEmpty = arr => Array.isArray(arr) && arr.length > 0;

isNotEmpty([1, 2, 3]);
// Result: true
```

**Get Selected Text**

```
const getSelectedText = () => window.getSelection().toString();

getSelectedText();
```

**Shuffle an Array**

```
const shuffleArray = (arr) => arr.sort(() => 0.5 - Math.random());

console.log(shuffleArray([1, 2, 3, 4]));
// Result: [ 1, 4, 3, 2 ]
```
