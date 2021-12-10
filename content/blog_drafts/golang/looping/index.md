---
title: Looping
date: "2021-11-01T23:22:03.284Z"
description: 'Looping in Go'
inHome: false
---

Loops are used to execute a block of statements repeatedly based on a condition. 

Most of the programming languages provide 3 types of loops

- `for`
- `while`
- `do while`
 
But Go supports only `for` loop.

The syntax of a `for` loop is

```go
for initialisation_expression; evaluation_expression; iteration_expression {
    // one or more statement
}
```

The `initialisation_expression` is executed first (and only once).

Then the `evaluation_expression` is evaluated and if it's `true` the code inside the block is executed.

The `iteration_expression` is executed, and the evaluation_expression is evaluated again. If it's `true` the statement block gets executed again.

This will continue until the `evaluation_expression` becomes `false`.

Copy the below program into a file and execute it to see the for loop printing numbers from 1 to 5

```go
package main

import "fmt"

func main() {
	var i int
	for i = 1; i <= 5; i++ {
		fmt.Println(i)
	}
}
```

Output is

```
1
2
3
4
5
```