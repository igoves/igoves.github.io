---
title: "Отправка почты Sendmail SMTP яндекс на Golang"
date: "2020-08-27"
categories: 
  - "go"
tags: 
  - "sendmail"
  - "smtp"
  - "yandex"
---

```
package main

import (
	"crypto/tls"
	"fmt"
	"log"
	"net"
	"net/mail"
	"net/smtp"
)

func sendmail(toEmail string, subj string, body string) {

	from := mail.Address{Name: "Name", Address: "no-replay@mail.com"}
	to := mail.Address{Name: "", Address: toEmail}

	headers := make(map[string]string)
	headers["From"] = from.String()
	headers["To"] = to.String()
	headers["Subject"] = subj

	message := ""
	for k, v := range headers {
		message += fmt.Sprintf("%s: %s\r\n", k, v)
	}
	message += "\r\n" + body

	servername := "smtp.yandex.ru:465"

	host, _, _ := net.SplitHostPort(servername)

	auth := smtp.PlainAuth("", "LOGIN", "PASSWORD", host)

	tlsconfig := &tls.Config{
		InsecureSkipVerify: true,
		ServerName:         host,
	}

	conn, err := tls.Dial("tcp", servername, tlsconfig)
	if err != nil {
		log.Panic(err)
	}

	a, err := smtp.NewClient(conn, host)
	if err != nil {
		log.Panic(err)
	}

	// Auth
	if err = a.Auth(auth); err != nil {
		log.Panic(err)
	}

	// To && From
	if err = a.Mail(from.Address); err != nil {
		log.Panic(err)
	}

	if err = a.Rcpt(to.Address); err != nil {
		log.Panic(err)
	}

	// Data
	w, err := a.Data()
	if err != nil {
		log.Panic(err)
	}

	_, err = w.Write([]byte(message))
	if err != nil {
		log.Panic(err)
	}

	err = w.Close()
	if err != nil {
		log.Panic(err)
	}

	a.Quit()

}
```
