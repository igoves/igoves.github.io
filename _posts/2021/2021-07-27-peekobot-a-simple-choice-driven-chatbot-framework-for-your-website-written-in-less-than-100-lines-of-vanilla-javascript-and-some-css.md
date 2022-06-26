---
title: "peekobot - a simple, choice-driven chatbot framework for your website written in less than 100 lines of vanilla JavaScript (and some CSS)"
date: ""
categories: 
  - "js"
---

![peekobot - a simple, choice-driven chatbot framework for your website written in less than 100 lines of vanilla JavaScript (and some CSS)](images/1578084293_screenshot_2020-01-03_22-42-10.png "peekobot - a simple, choice-driven chatbot framework for your website written in less than 100 lines of vanilla JavaScript (and some CSS)")

  

```
const chat = {
    1: {
        text: 'Good morning sir',
        next: 2
    },
    2: {
        text: 'Would you like tea or coffee with your breakfast?',
        options: [
            {
                text: 'Tea',
                next: 3
            },
            {
                text: 'Coffee',
                next: 4
            }
        ]
    },
    3: {
        text: 'Splendid - a fine drink if I do say so myself.'
    },
    4: {
        text: 'As you wish, sir'
    }
}
```

  
[https://github.com/Peekobot/peekobot](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1BlZWtvYm90L3BlZWtvYm90) | [example page](https://dev.xfor.top/go/aHR0cHM6Ly9wZWVrb2JvdC5naXRodWIuaW8vcGVla29ib3Qv)
