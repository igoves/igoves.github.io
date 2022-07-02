---
title: "Работа с Mysql  в GO"
date: "2020-11-10"
categories: 
  - "go"
tags: 
  - "mysql"
---

```
package main

import (
	"database/sql"
	"fmt"

	_ "github.com/go-sql-driver/mysql"
)

func main() {
	db, err := sql.Open("mysql", "root:root@/dbname")

	if err != nil {
		panic(err)
	}
	defer db.Close()

	result, err := db.Exec("insert into Orders (name, email, cart) values (?, ?, ?)",
		"iPhone X", "Apple", 72000)
	if err != nil {
		panic(err)
	}
	fmt.Println(result.LastInsertId())
	fmt.Println(result.RowsAffected())
}
```
