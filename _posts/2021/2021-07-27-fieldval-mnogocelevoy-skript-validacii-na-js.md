---
title: "FieldVal - многоцелевой скрипт валидации на JS"
date: ""
categories: 
  - "js"
---

![FieldVal - многоцелевой скрипт валидации на JS](images/1423477442_untitled-5.png "FieldVal - многоцелевой скрипт валидации на JS")

  

```
function validate(parameters){      if(parameters.username === undefined){        return "Username is missing";    }    if(typeof parameters.username !== "string"){        return "Username must be a string";    }    if(typeof parameters.username.length < 3){        return "Username must be at least 3 characters long";    }    if(parameters.id === undefined){        return "Id is missing";    }    if(typeof parameters.id !== "number" || parameters.id % 1 !== 0){        return "Id must be an integer";    }    if(parameters.id < 1){        return "Id must be greater than 1";    }}
```

  
[http://www.fieldval.com/](https://dev.xfor.top/go/aHR0cDovL3d3dy5maWVsZHZhbC5jb20v)
