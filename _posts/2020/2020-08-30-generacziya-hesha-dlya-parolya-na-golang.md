---
title: "Генерация хеша для пароля на Golang"
date: "2020-08-30"
categories: 
  - "go"
tags: 
  - "generator-2"
  - "hash"
  - "password"
---

```
package main

import (
	"golang.org/x/crypto/bcrypt"
)

func HashPassword(password string) (string, error) {
	hash, err := bcrypt.GenerateFromPassword([]byte(password), 15)
	return string(hash), err
}
```
