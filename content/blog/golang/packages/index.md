---
title: Packages
date: "2021-11-02T23:22:03.284Z"
description: 'Packages in Go?'
inHome: false
---

Packages are used to organize the code. In a big project, it is not feasible to write code in a single file.

Go allow us to organize the code under different packages. This increases code readability and reusability. 

An executable Go program should contain a package named main and the program execution starts from the function named main.

You can import other packages in our program using the syntax

```go
import package_name
```

We will see and discuss how to create and use packages in the following example.

Create a file called `package_example.go` and add the below code:

```go
package main

import (
	"calculation" // The package to be created
	"fmt"
)

func main() {
	x, y := 15, 10

	// The package will have function Do_add()
	sum := calculation.Do_add(x, y)

	fmt.Println("Sum", sum)
}
```

In the above program `fmt` is a package which Go provides us mainly for I/O purposes.

Also, you can see a package named `calculation`.

Inside the `main()` you can see a step `sum := calculation.Do_add(x,y)`. It means you are invoking the function `Do_add` from package `calculation`.

### Creating a new package

First, you should create the package `calculation` inside a folder with the same name under `src` folder of the go.

The installed path of go can be found from the PATH variable.

For mac, find the path by executing `echo $PATH`.

Navigate to to the `src` folder (`/usr/local/go/src` for mac and `C:\Go\src` for windows).

Now from the code, the package name is `calculation`. 

Go requires the package should be placed in a directory of the same name under `src` directory. Create a directory named `calculation` in `src` folder.

Create a file called `calc.go` (You can give any name, but the package name in the code matters. Here it should be calculation) inside calculation directory and add the below code

```go
package calculation

func Do_add(num1 int, num2 int) int {
	sum := num1 + num2
	return sum
}
```

Run the command `go install` from the `calculation` directory which will compile the `calc.go`.

Now go back to `package_example.go` and run `go run package_example.go`. 

The output will be

```
Sum 25.
```

Note that the name of the function `Do_add` starts with a capital letter. This is because in Go if the function name starts with a capital letter it means other programs can see (access) it else other programs cannot access it. If the function name was `do_add`, then you would have got the error `cannot refer to unexported name calculation.calc..`.
