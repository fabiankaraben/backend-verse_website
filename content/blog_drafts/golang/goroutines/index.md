---
title: Goroutines
date: "2021-11-03T22:22:03.284Z"
description: 'Goroutines in Go?'
inHome: false
---

A goroutine is a function which can run concurrently with other functions.

Usually when a function is invoked the control gets transferred into the called function, and once its completed execution control returns to the calling function. The calling function then continues its execution. 

The calling function waits for the invoked function to complete the execution before it proceeds with the rest of the statements.

But in the case of goroutine, the calling function will not wait for the execution of the invoked function to complete. It will continue to execute with the next statements. 

You can have multiple goroutines in a program.

Also, the main program will exit once it completes executing its statements and it will not wait for completion of the goroutines invoked.

Goroutine is invoked using keyword go followed by a function call.
Example:

```go
go add(x,y)
```

You will understand goroutines with the below examples. Execute the below program

```go
package main

import "fmt"

func display() {
	for i := 0; i < 5; i++ {
		fmt.Println("In display")
	}
}
func main() {
	// Invoking the goroutine display()
	go display()
	
	// The main() continues without waiting for display()
	for i := 0; i < 5; i++ {
		fmt.Println("In main")
	}
}
```

The output will be

```
In main
In main
In main
In main
In main
```

Here the main program completed execution even before the goroutine started.

The `display()` is a goroutine which is invoked using the syntax go `function_name(parameter list)`

In the above code, the `main()` doesn't wait for the `display()` to complete, and the `main()` completed its execution before the display() executed its code. So the print statement inside `display()` didn't get printed.

Now we modify the program to print the statements from `display()` as well.

We add a time delay of 2 sec in the for loop of `main()` and a 1 sec delay in the for loop of the `display()`.

```go
package main

import (
	"fmt"
	"time"
)

func display() {
	for i := 0; i < 5; i++ {
		time.Sleep(1 * time.Second)
		fmt.Println("In display")
	}
}
func main() {
	// Invoking the goroutine display()
	go display()
	for i := 0; i < 5; i++ {
		time.Sleep(2 * time.Second)
		fmt.Println("In main")
	}
}
```

The output will be somewhat similar to

```
In display
In main
In display
In display
In main
In display
In display
In main
In main
In main
```

Here You can see both loops are being executed in an overlapping fashion because of the concurrent execution.

