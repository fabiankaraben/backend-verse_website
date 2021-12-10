---
title: Constants
date: "2021-11-01T23:02:03.284Z"
description: 'Constants in Go?'
inHome: false
---

Constant variables are those variables whose value cannot be changed once assigned. 

A constant in Go is declared by using the keyword `const`.

Create a file called `constant.go` and with the following code:

```go
package main

import (
	"fmt"
)

func main() {
	const b = 10
	fmt.Println(b)
	b = 30
	fmt.Println(b)
}
```

Execute `go run constant.go` to see the result as:

```
.constant.go:7:4: cannot assign to b
```
