---
title: Writing Files
date: "2021-11-03T23:59:03.284Z"
description: 'Writing Files in Go?'
inHome: false
---

You will see this with a program

```go
package main

import (
	"fmt"
	"os"
)

func main() {
	f, err := os.Create("file1.txt")
	if err != nil {
		fmt.Println(err)
		return
	}
	l, err := f.WriteString("Write Line one")
	if err != nil {
		fmt.Println(err)
		f.Close()
		return
	}
	fmt.Println(l, "bytes written")
	err = f.Close()
	if err != nil {
		fmt.Println(err)
		return
	}
}
```

Here a file is created, `test.txt`. 

If the file already exists then the contents of the file are truncated. `Writeline()` is used to write the contents to the file.

After that, You closed the file using `Close()`.
