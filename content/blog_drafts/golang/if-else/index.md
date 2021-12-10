---
title: If and Else
date: "2021-11-01T23:42:03.284Z"
description: 'If and Else in Go'
inHome: false
---

*If else* is a conditional statement. The syntax is

```go
if condition {
    // statements_1
} else {
    // statements_2
}
```

Here the condition is evaluated and if it's `true` `statements_1` will be executed else `statements_2` will be executed.

You can use if statement without `else` also. 

You also can have chained `if` `else` statements.

The below programs will explain more about `if` `else`.

Execute the below program. It checks if a number, `x`, is less than `10`. If so, it will print `x is less than 10`

```go
package main

import "fmt"

func main() {
	var x = 50
	if x < 10 {
		//Executes if x < 10
		fmt.Println("x is less than 10")
	}
}
```

Here since the value of `x` is greater than `10`, the statement inside the `if` block condition will not executed.

Now see the below program. We have an `else` block which will get executed on the failure of if evaluation.

```go
package main

import "fmt"

func main() {
	var x = 50
	if x < 10 {
		//Executes if x is less than 10
		fmt.Println("x is less than 10")
	} else {
		//Executes if x >= 10
		fmt.Println("x is greater than or equals 10")
	}
}
```

This program will give you output `x is greater than or equals 10`.

Now we will see a program with multiple `if` `else` blocks (chained `if` `else`).

Execute the below example. It checks whether a number is less than
`10` or is between `10`-`90` or greater than `90`.

```go
package main

import "fmt"

func main() {
	var x = 100
	if x < 10 {
		//Executes if x is less than 10
		fmt.Println("x is less than 10")
	} else if x >= 10 && x <= 90 {
		//Executes if x >= 10 and x<=90fmt.Println("x is between 10 and 90")
	} else {
		//Executes if both above cases fail i.e x>90
		fmt.Println("x is greater than 90")
	}
}
```

Here the first `if` condition checks whether `x` is less than `10` and it's not. So it checks the next condition (`else if`) whether it's between `10` and `90` which is also `false`. So it then executes the block under the `else` section which gives the output `x is greater than 90`.