---
title: Error Handling
date: "2021-11-03T23:32:03.284Z"
description: 'Error Handling in Go?'
inHome: false
---

Errors are abnormal conditions like closing a file which is not opened, open a file which doesn't exist, etc. Functions usually return errors as the last return value.

The below example explains more about the error.

```go
package main

import (
	"fmt"
	"os"
)

// Function accepts a filename and tries to open it.
func fileopen(name string) {
	f, er := os.Open(name)
	// er will be nil if the file exists else it returns an error object
	if er != nil {
		fmt.Println(er)
		return
	} else {
		fmt.Println("file opened", f.Name())
	}
}
func main() {
	fileopen("invalid.txt")
}
```

The output will be:

```
open /invalid.txt: no such file or directory.
```

Here we tried to open a non-existing file, and it returned the error to er variable. If the file is valid, then the error will be null.