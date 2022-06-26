---
title: "GZIP сжатия в NGINX"
date: ""
categories: 
  - "note"
---

/etc/nginx/nginx.conf  

```
	gzip                          on;
	gzip_buffers                  4 64k;
	gzip_comp_level               6;
	gzip_disable                  "msie6";
	#gzip_min_length              32768;
	gzip_proxied                  any;
	#gzip_static                  off;
	#gzip_http_version            1.1;
	gzip_vary                     on;
	gzip_types                    text/plain text/css application/x-javascript text/xml application/xml application/xml+rss text/javascript application/json;
```
