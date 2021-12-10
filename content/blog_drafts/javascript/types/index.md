---
title: Types
date: "2021-11-04T11:42:03.284Z"
description: 'Types in JavaScript'
inHome: false
---

Types are used to represent the type of data.

Primarily, there are two categories of types.

1. Primitive types
2. Reference types

#### Primitive Types

Numbers, strings and Boolean values considered as primitive types.

In addition to these, special values null, undefined are also considered as primitive types.

#### Reference Types

Objects and arrays are considered as reference types. An object is a collection of name and value pairs. Array is a collection of elements.

One more thing to note is that JavaScript treats functions also objects.

```javascript
var a = 10;
var b = 10.01;
var c = true;
var d = "Hello World";
var e = {
    name : "Hari krishna",
    city : "Bangalore"
};
var f = [2, 3, 5, 7];

console.log("a = " + a + " Type of a = " + (typeof a));
console.log("b = " + b + " Type of b = " + (typeof b));
console.log("c = " + c + " Type of c = " + (typeof c));
console.log("d = " + d + " Type of d = " + (typeof d));
console.log("e = " + e + " Type of e = " + (typeof e));
console.log("f = " + f + " Type of f = " + (typeof f));
```

You can able to see following messages in the browser console.

```
a = 10 Type of a = number
b = 10.01 Type of b = number
c = true Type of c = boolean
d = Hello World Type of d = string
e = [object Object] Type of e = object
f = 2,3,5,7 Type of f = object
```

As you see the output, JavaScript treats both integer and float values as type number and arrays, objects are treated as type object.