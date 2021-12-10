---
title: Custom Errors
date: "2021-11-03T23:42:03.284Z"
description: 'Custom Errors in Go?'
inHome: false
---

Using this feature, you can create custom errors. This is done by using `New()` of error package. 

We will rewrite the above program to make use of custom errors.

Run the below program

```go
package main

import (
	"errors"
	"fmt"
	"os"
)

// Function accepts a filename and tries to open it.
func fileopen(name string) (string, error) {
	f, er := os.Open(name)
	// er will be nil if the file exists else it returns an error object
	if er != nil {
		// Created a new error object and returns it
		return "", errors.New("Custom error message: File name is wrong")
	} else {
		return f.Name(), nil
	}
}
func main() {
	// Receives custom error or nil after trying to open the file
	filename, error := fileopen("invalid.txt")
	if error != nil {
		fmt.Println(error)
	} else {
		fmt.Println("file opened", filename)
	}
}
```

The output will be:

```
Custom error message:File name is wrong
```

Here the area() returns the area of a square. If the input is less than 1 then area() returns an error message.