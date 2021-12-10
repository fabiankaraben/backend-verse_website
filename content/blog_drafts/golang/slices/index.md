---
title: Slices
date: "2021-11-02T22:42:03.284Z"
description: 'Slices in Go?'
inHome: false
---

A slice is a portion or segment of an array. Or it is a view or partial view of an underlying array to which it points.

You can access the elements of a slice using the slice name and index number just as you do in an array. 

You cannot change the length of an array, but you can change the size of a slice.

Contents of a slice are actually the pointers to the elements of an array. It means if you change any element in a slice, the underlying array contents also will be affected.

The syntax for creating a slice is:

```go
var slice_name []type = array_name[start:end]
```

This will create a slice named `slice_name` from an array named `array_name` with the elements at the index `start` to `end` - 1.

Execute the below program. The program will create a slice from the array and print it. Also, you can see that modifying the contents in the slice will modify the actual array.

```go
package main

import "fmt"

func main() {
	// Declaring array
	a := [5]string{"one", "two", "three", "four", "five"}
	fmt.Println("Array after creation:", a)

	// Created a slice named b
	var b []string = a[1:4]
	fmt.Println("Slice after creation:", b)

	// Changed the slice data
	b[0] = "changed"
	fmt.Println("Slice after modifying:", b)
	fmt.Println("Array after slice modification:", a)
}
```

This will print result as

```
Array after creation: [one two three four five]
Slice after creation: [two three four]
Slice after modifying: [changed three four]
Array after slice modification: [one changed three four five]
```

There are certain functions which you can apply on slices

- `len(slice_name)` - returns the length of the slice
- `append(slice_name, value_1, value_2)` - It is used to append value_1 and value_2 to an existing slice.
- `append(slice_nale1,slice_name2...)` - appends slice_name2 to slice_name1

Execute the following program.

```go
package main

import "fmt"

func main() {
	a := [5]string{"1", "2", "3", "4", "5"}
	slice_a := a[1:3]

	b := [5]string{"one", "two", "three", "four", "five"}
	slice_b := b[1:3]

	fmt.Println("Slice_a:", slice_a)
	fmt.Println("Slice_b:", slice_b)

	fmt.Println("Length of slice_a:", len(slice_a))
	fmt.Println("Length of slice_b:", len(slice_b))

	slice_a = append(slice_a, slice_b...) // appending slice
	fmt.Println("New Slice_a after appending slice_b :", slice_a)

	slice_a = append(slice_a, "text1") // appending value
	fmt.Println("New Slice_a after appending text1 :", slice_a)
}
```

The output will be

```
Slice_a: [2 3]
Slice_b: [two three]
Length of slice_a: 2
Length of slice_b: 2
New Slice_a after appending slice_b : [2 3 two three]
New Slice_a after appending text1 : [2 3 two three text1]
```

The program first creates 2 slices and printed its length. Then it appended one slice to other and then appended a string to the resulting slice.
