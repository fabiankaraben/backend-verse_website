---
title: Variables
date: "2021-11-01T22:42:03.284Z"
description: 'Variables in Go?'
inHome: false
---

Variables point to a memory location which stores some kind of value.

The `type` parameter (in the below syntax) represents the type of value that can be stored in the memory location.

Variable can be declared using the syntax:

``` go
var <variable_name> <type>
```

Once You declare a variable of a type You can assign the variable to any value of that type.

You can also give an initial value to a variable during the declaration itself using

``` go
var <variable_name> <type> = <value>
```

If You declare the variable with an initial value, Go infer the type of the variable from the type of value assigned.

So, you can omit the type during the declaration using the syntax

```go
var <variable_name> = <value>
```

Also, you can declare multiple variables with the syntax

```go
var <variable_name1>, <variable_name2> = <value1>, <value2>
```

The program below has some examples of variable declarations

```go
package main

import "fmt"

func main() {
	// Declaring a integer variable x
	var x int
	x = 3                // Assigning x the value 3
	fmt.Println("x:", x) // Prints 3

	// Declaring a integer variable y with value 20 in a single statement and prints it
	var y int = 20
	fmt.Println("y:", y)

	// Declaring a variable z with value 50 and prints it
	// Here type int is not explicitly mentioned
	var z = 50
	fmt.Println("z:", z)

	// Multiple variables are assigned in single line- i with an integer and j with a string
	var i, j = 100, "hello"
	fmt.Println("i and j:", i, j)
}

```

The output will be

```
x: 3
y: 20
z: 50
i and j: 100 hello
```

Go also provides an easy way of declaring the variables with value by omitting the var keyword using

```go
<variable_name> := <value>
```

Note that You used `:=` instead of `=`.

You cannot use `:=` just to assign a value to a variable which is already declared.

`:=` is used to declare and assign value.

Create a file called `assign.go` with the following code

```go
package main

import (
	"fmt"
)

func main() {
	a := 20
	fmt.Println(a)

	// Gives error since a is already declared
	a := 30
	fmt.Println(a)
}
```

Execute `go run assign.go` to see the result as:

```
./assign.go:7:4: no new variables on left side of :=
```

Variables declared without an initial value will have of `0` for numeric types, `false` for Boolean and empty string for strings.
