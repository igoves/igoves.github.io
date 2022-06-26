---
title: "is.js - библиотека проверок"
categories: 
  - "js"
---

bundle:nil, , is.null( value ), is.undefined( value ), is.exist( value ), is.nil( value ), bundle:number, , is.number( value ), is.numeral( value ), is.nan( value ), is.odd( number ), is.even( number ), is.finite( number ), is.infinite( number ), is.integer( number ), is.safeInteger( number ), bundle:string, , is.string( value ), is.emptyString( string ), is.substring( substring , string , \[offset=0\] ), is.prefix( prefix , string ), is.suffix( suffix , string ) и тд  
Пример

```
const is = require( '@pwn/is' )

is.array( [] ) // true
is.not.integer( 0 ) // false
is.propertyDefined( { foo : { bar : 0 } } , 'foo.bar' ) // true
is.equal( [ 1 , [ 2 , 3 ] ] , [ 1 , [ 2 , 3 ] ] ) // false
is.deepEqual( [ 1 , [ 2 , 3 ] ] , [ 1 , [ 2 , 3 ] ] ) // true

// use a third-party bundle
is.use( require( 'path/to/some/math/bundle' ) )
is.prime( 7 ) // true
```

  
[https://github.com/pwnn/is.js/](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3B3bm4vaXMuanMv)
