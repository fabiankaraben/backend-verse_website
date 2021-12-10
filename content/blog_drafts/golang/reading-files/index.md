---
title: Reading Files
date: "2021-11-03T23:52:03.284Z"
description: 'Reading Files in Go?'
inHome: false
---

Files are used to store data. Go allows us to read data from the files.

First create a file, `data.txt`, in your present directory with the below content.

```
Line one
Line two
Line three
```

Now run the below program to see it prints the contents of the entire file as output

```go
package main

import (
	"fmt"
	"io/ioutil"
)

func main() {
	data, err := ioutil.ReadFile("data.txt")
	if err != nil {
		fmt.Println("File reading error", err)
		return
	}
	fmt.Println("Contents of file:", string(data))
}
```

Here the `data, err := ioutil.ReadFile("data.txt")` reads the data and returns a byte sequence. While printing it is converted to string format.
