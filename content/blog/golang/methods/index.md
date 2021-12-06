---
title: Methods
date: "2021-11-03T21:42:03.284Z"
description: 'Methods in Go?'
inHome: false
---

A method is a function with a receiver argument. Architecturally, it's between the func keyword and method name.

The syntax of a method is

```go
package main

import "fmt"

// Declared the structure named emp
type emp struct {
	name    string
	address string
	age     int
}

// Declaring a function with receiver of the type emp
func (e emp) display() {
	fmt.Println(e.name)
}
func main() {
	// Declaring a variable of type emp
	var empdata1 emp

	// Assign values to membersempdata1.name = "John"
	empdata1.address = "Street-1, London"
	empdata1.age = 30

	// Declaring a variable of type emp and assign values to members
	empdata2 := emp{
		"Sam", "Building-1, Paris", 25}

	//Invoking the method using the receiver of the type emp
	// syntax is variable.methodname()
	empdata1.display()
	empdata2.display()
}
```

Go is not an object oriented language and it doesn't have the concept of class.

Methods give a feel of what you do in object oriented programs where the functions of a class are invoked using the syntax `objectname.functionname()`.

