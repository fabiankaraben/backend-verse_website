---
title: Structures
date: "2021-11-03T21:22:03.284Z"
description: 'Structures in Go?'
inHome: false
---

A Structure is a user defined datatype which itself contains one more element of the same or different type.

Using a structure is a 2 step process.

First, create (declare) a structure type.

Second, create variables of that type to store values.

Structures are mainly used when you want to store related data together.

Consider a piece of employee information which has name, age, and address. You can handle this in 2 ways:

1. Create 3 arrays - one array stores the names of employees, one stores age and the third one stores age.
2. Declare a structure type with 3 fields- name, address, and age. Create an array of that structure type where each element is a structure object having
name, address, and age.

The first approach is not efficient. In these kinds of scenarios, structures are more convenient.

The syntax for declaring a structure is:

```go
type structname struct {
    variable_1 variable_1_type
    variable_2 variable_2_type
    variable_n variable_n_type
}
```

An example of a structure declaration is

```go
type emp struct {
    name string
    address string
    age int
}
```

Here a new user defined type named `emp` is created. Now, you can create variables of the type `emp` using the syntax

```go
var variable_name struct_name
```

An example is:

```go
var empdata1 emp
```

You can set values for the `empdata1` as

```go
empdata1.name = "John"
empdata1.address = "Street-1, Sydney"
empdata1.age = 30
```

You can also create a structure variable and assign values by

```go
empdata2 := emp{"Sam", "Building-1, Zurich", 25}
```

Here, you need to maintain the order of elements. Sam will be mapped to name, next element to address and the last one to age.

Execute the code below

```go
package main

import "fmt"

// Declared the structure named emp
type emp struct {
	name    string
	address string
	age     int
}

// Function which accepts variable of emp type and prints name property
func display(e emp) {
	fmt.Println(e.name)
}
func main() {
	// Declares a variable, empdata1, of the type emp
	var empdata1 emp

	// Assign values to members of empdata1
	empdata1.name = "John"
	empdata1.address = "Street-1, London"
	empdata1.age = 30

	// Declares and assign values to variable empdata2 of type emp
	empdata2 := emp{"Sam", "Building-1, Paris", 25}

	// Prints the member name of empdata1 and empdata2 using display function
	display(empdata1)
	display(empdata2)
}
```

Output

```
John
Sam
```