---
title: "Деламе вот такой путь на CSS"
categories: 
  - "css"
---

![Деламе вот такой путь на CSS](images/1385315341_untitled-10.jpg "Деламе вот такой путь на CSS")

  

```
<!DOCTYPE html><html><head><meta charset="utf-8" /><title>CSS Breadcrumbs demo</title><link href="style.css" rel="stylesheet" /></head><body><div id="crumbs">	<ul>		<li><a href="#1">One</a></li>		<li><a href="#2">Two</a></li>		<li><a href="#3">Three</a></li>		<li><a href="#4">Four</a></li>		<li><a href="#5">Five</a></li>	</ul></div></body></html>
```

  
И собственно сам CSS  

```
#crumbs {	text-align: center;}	#crumbs ul {		list-style: none;		display: inline-table;	}		#crumbs ul li {			display: inline;		}			#crumbs ul li a {			display: block;			float: left;			height: 50px;			background: #3498db;			text-align: center;			padding: 30px 40px 0 80px;			position: relative;			margin: 0 10px 0 0; 						font-size: 20px;			text-decoration: none;			color: #fff;		}			#crumbs ul li a:after {				content: "";  				border-top: 40px solid transparent;	 			border-bottom: 40px solid transparent;	  			border-left: 40px solid #3498db;				position: absolute; right: -40px; top: 0;				z-index: 1;			}						#crumbs ul li a:before {				content: "";  				border-top: 40px solid transparent;	  			border-bottom: 40px solid transparent;	  			border-left: 40px solid #d4f2ff;				position: absolute; left: 0; top: 0;			}					#crumbs ul li:first-child a {					border-top-left-radius: 10px; border-bottom-left-radius: 10px;				}				#crumbs ul li:first-child a:before {					display: none; 				}								#crumbs ul li:last-child a {					padding-right: 80px;					border-top-right-radius: 10px; border-bottom-right-radius: 10px;				}				#crumbs ul li:last-child a:after {					display: none; 				}						#crumbs ul li a:hover {				background: #fa5ba5;			}				#crumbs ul li a:hover:after {					border-left-color: #fa5ba5;				}		
```

  
[ДЕМО](https://dev.xfor.top/go/aHR0cDovL2xpbmUyNS5jb20vd3AtY29udGVudC91cGxvYWRzLzIwMTMvYnJlYWRjcnVtYnMvZGVtby9kZW1vLmh0bWw%3D)
