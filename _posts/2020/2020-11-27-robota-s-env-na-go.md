---
title: "Работа с Env на GO"
date: "2020-11-27"
categories: 
  - "go"
tags: 
  - "file"
---

```
package main

import (
    "fmt"
    "log"

    "github.com/craicoverflow/go-environment-variables-example/config"
    "github.com/joho/godotenv"
)

func init() {
    if err := godotenv.Load(); err != nil {
		log.Print("No .env file found")
    }
}

func main() {
    conf := config.New()

    fmt.Println(conf.GitHub.Username)
    fmt.Println(conf.GitHub.APIKey)
    fmt.Println(conf.DebugMode)
    fmt.Println(conf.MaxUsers)

}
```
