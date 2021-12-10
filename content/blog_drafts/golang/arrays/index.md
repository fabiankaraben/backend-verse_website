---
title: Arrays
date: "2021-11-02T22:22:03.284Z"
description: 'Arrays in Go?'
inHome: false
---

Array represents a fixed size, named sequence of elements of the same type.

You cannot have an array which contains both integer and characters in it.

You cannot change the size of an array once You define the size.

The syntax for declaring an array is:

```go
var arrayname [size]type
```

Each array element can be assigned value using the syntax

```go
arrayname[index] = value
```

Array index starts from `0` to `size - 1`.

You can assign values to array elements during declaration using the syntax

```go
arrayname := [size]type{value_0, value_1, ..., value_size-1}
```

You can also ignore the size parameter while declaring the array with values by replacing size with `...` and the compiler will find the length from the number of values. Syntax is:

```go
arrayname := [...]type{value_0, value_1, ..., value_size-1}
```

You can find the length of the array by using the syntax `len(arrayname)`.

Execute the below example to understand the array

```go
package main

import "fmt"

func main() {
	// Declaring a string array of size 3 and adding elements
	var numbers [3]string
	numbers[0] = "One"
	numbers[1] = "Two"
	numbers[2] = "Three"

	fmt.Println(numbers[1])   // Prints Two
	fmt.Println(len(numbers)) // Prints 3
	fmt.Println(numbers)      // Prints [One Two Three]

	// Creating an integer array and the size of the array is defined by the number of elements
	directions := [...]int{1, 2, 3, 4, 5}

	fmt.Println(directions)      // Prints [1 2 3 4 5]
	fmt.Println(len(directions)) // Prints 5

	// Executing the below commented statement prints invalid array index 5 (out of bounds for 5-element array)
	//fmt.Println(directions[5])
}
```

Output

```
Two
3
[One Two Three]
[1 2 3 4 5]
5
```