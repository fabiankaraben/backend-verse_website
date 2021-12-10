---
title: Arithmetic Operators
date: "2021-11-04T12:22:03.284Z"
description: 'Arithmetic Operators in JavaScript'
inHome: false
---

Following table summarizes Arithmetic operators supported by Javascript.

| Operator | Description                                  |
| -------- | -------------------------------------------- |
| +        | Additon (also used for String concatenation) |
| -        | Subtraction                                  |
| /        | Division                                     |
| *        | Multiplication                               |
| %        | Gives Remainder                              |

#### Example

```javascript
var a = 23 ;
var b = 3 ;

console.log( "a = " + a );
console.log( "b = " + b );
console.log( "a + b = " + (a + b) );
console.log( "a - b = " + (a - b) );
console.log( "a * b = " + (a * b) );
console.log( "a / b = " + (a / b) );
console.log( "a % b = " + (a % b) );
```

Output:

```
a = 23 
b = 3
a + b = 26
a - b = 20
a * b = 69
a / b = 7.666666666666667
a % b = 2 
```

Note: Unlike languages like Java, integer division in JavaScript returns float value.