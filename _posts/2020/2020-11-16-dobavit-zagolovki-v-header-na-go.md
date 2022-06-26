---
title: "Добавить заголовки в Header на Go"
date: "2020-11-16"
categories: 
  - "go"
---

С помощью Gin

```
func Options() gin.HandlerFunc {
	return func(ctx *gin.Context) {
		if ctx.Request.Method != "OPTIONS" {
			ctx.Next()
		} else {
			ctx.Header("Access-Control-Allow-Origin", "*")
			ctx.Header("Access-Control-Allow-Methods", "GET,POST,PUT,PATCH,DELETE,OPTIONS")
			ctx.Header("Access-Control-Allow-Headers", "authorization, origin, content-type, accept")
			ctx.Header("Allow", "HEAD,GET,POST,PUT,PATCH,DELETE,OPTIONS")
			ctx.Header("Content-Type", "application/json")
			ctx.AbortWithStatus(200)
		}
	}
}
```

Или например отключить кэш

```
func NoCache() gin.HandlerFunc {
	return func(ctx *gin.Context) {
		ctx.Header("Cache-Control", "no-cache, no-store, max-age=0, must-revalidate, value")
		ctx.Header("Expires", "Thu, 01 Jan 1970 00:00:00 GMT")
		ctx.Header("Last-Modified", time.Now().UTC().Format(http.TimeFormat))
		ctx.Next()
	}
}
```
