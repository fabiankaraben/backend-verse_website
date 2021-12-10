---
title: Pointers
date: "2021-11-03T21:02:03.284Z"
description: 'Pointers in Go?'
inHome: false
---

Before explaining pointers let's will first discuss `&` operator. The `&` operator is used to get the address of a variable. It means `&a` will print the memory address of variable `a`.

Execute the below program to display the value of a variable and the address of that variable

```go
package main

import "fmt"

func main() {
	a := 20
	fmt.Println("Address:", &a)
	fmt.Println("Value:", a)
}
```

The result will be

```
Address: 0xc000078008
Value: 20
```

A pointer variable stores the memory address of another variable.

You can define a pointer using the syntax

```go
var variable_name *type
```

The asterisk (`*`) represents the variable is a pointer.

You will understand more by executing the below program

```go
package main

import "fmt"

func main() {
	// Create an integer variable a with value 20
	a := 20
	
	// Create a pointer variable b and assigned the address of a
	var b *int = &a

	// Print address of a(&a) and value of a
	fmt.Println("Address of a:", &a)
	fmt.Println("Value of a:", a)

	// Print b which contains the memory address of a i.e. &a
	fmt.Println("Address of pointer b:", b)

	// *b prints the value in memory address which b contains i.e. the value of a
	fmt.Println("Value of pointer b", *b)

	// Increment the value of variable a using the variable b
	*b = *b + 1

	//Prints the new value using a and *b
	fmt.Println("Value of pointer b", *b)
	fmt.Println("Value of a:", a)
}
```

The output will be

```
Address of a: 0x416020
Value of a: 20
Address of pointer b: 0x416020
Value of pointer b 20
Value of pointer b 21
Value of a: 21
```
