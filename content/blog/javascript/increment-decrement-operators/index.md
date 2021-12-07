---
title: Increment Decrement Operators
date: "2021-11-04T12:42:03.284Z"
description: 'Increment Decrement Operators in JavaScript'
inHome: false
---

#### Increment & decrement operators

- `++` Increment operator; increments a value by 1
- `--` Decrement operator; decrements a value by 1

#### Pre increment

Syntax:

```javascript
++variable
```

Pre increment operator increments the variable value by 1 immediately.

#### Post increment

Syntax:

```javascript
variable++
```

Post increment operator increments the variable value by 1 after executing the current statement.

#### Pre Decrement

Syntax:

```javascript
--variable
```

Pre decrement operator decrements the variable value by 1 immediately.

#### Post Decrement

Syntax:

```javascript
variable--
```

Post decrement operator decrements the variable value by 1 after executing the current statement.

#### Example

```javascript
var a = 23 ;
console.log( "a = " + a );
console.log( "a++ = " + (a++ ) );
console.log( "++a = " + ( ++a) );
console.log( "a-- = " + (a-- ) );
console.log( "--a = " + ( --a) );
```

Output:

```
a = 23
a++ = 23
++a = 25
a-- = 25
--a = 23
```