---
title: Comments
date: "2021-11-04T11:22:03.284Z"
description: 'Comments in JavaScript'
inHome: false
---

Comments are used to document the source code.

Comments in javaScript makes the program more readable. Comments are ignored by JavaScript.

Suppose you written thousand lines of program, with out proper documentation, after some time, for the owner of the application also, it is very difficult to figure out what was written.

Comments solve this problem:

By using comments, you can document your code at the time of writing program. Comments won't affect your program execution.

Comments simply document your code.

Javascript support 2 kinds of comments.

1. Single line comments
2. Multi line comments

#### Single line comment:

Single line comments starts with `//`

```javascript
// It is a single line comment
```

#### Multi Line comment

Multi line comments are encoded in `/* */`

```javascript
/* I am a mulltiline comment */
```

#### Example

```javascript
/*
JavaScript is weakly typed language
Author: Peter
*/

var a = 10;
console.log("Value of a is " + a);

a = "Hello World"; // Assigning string
console.log("Value of a is " + a);

a = true; // Assigning boolean
console.log("Value of a is " + a);

a = 10.09; // Assigning number
console.log("Value of a is " + a);
```