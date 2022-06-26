---
title: "spected - js скрипт валидации"
categories: 
  - "js"
---

Пример

```
import {
  compose,
  curry,
  head,
  isEmpty,
  length,
  not,
  prop,
} from 'ramda'

import spected from 'spected'

// predicates

const notEmpty = compose(not, isEmpty)
const hasCapitalLetter = a => /[A-Z]/.test(a)
const isGreaterThan = curry((len, a) => (a > len))
const isLengthGreaterThan = len => compose(isGreaterThan(len), prop('length'))


// error messages

const notEmptyMsg = field => `${field} should not be empty.`
const minimumMsg = (field, len) => `Minimum ${field} length of ${len} is required.`
const capitalLetterMag = field => `${field} should contain at least one uppercase letter.`

// rules

const nameValidationRule = [[notEmpty, notEmptyMsg('Name')]]

const randomValidationRule = [
  [isLengthGreaterThan(2), minimumMsg('Random', 3)],
  [hasCapitalLetter, capitalLetterMag('Random')],
]

const validationRules = {
  name: nameValidationRule,
  random: randomValidationRule,
}

spected(validationRules, {name: 'foo', random: 'Abcd'})
// {name: true, random: true}
```

  
[https://github.com/25th-floor/spected](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tLzI1dGgtZmxvb3Ivc3BlY3RlZA%3D%3D)
