---
title: "Унмаршалинг или парсинг JSON на golang"
date: "2020-10-06"
categories: 
  - "go"
tags: 
  - "json"
  - "marshaling"
---

```
package main

import (
	"encoding/json"
	"fmt"
)

func main() {

	type TmpData struct {
		Email string `json:"email"`
		Cart  []struct {
			Name  string `json:"name"`
			Price string `json:"price"`
			Count string `json:"count"`
			Total string `json:"total"`
		} `json:"cart"`
	}

	var tmpW TmpData

	empJson := `{"email":"asdf@adsf.com","cart":[{"name":"Товар 1","price":"79.99","count":1,"total":"79.99"},{"name":"Товар 2","price":"179.99","count":1,"total":"79.99"}]}`

	json.Unmarshal([]byte(empJson), &tmpW)

	fmt.Printf("%+v\n", tmpW.Cart[1].Name)

	for _, v := range tmpW.Cart {
		fmt.Println("value:", v.Name)
	}

}
```
