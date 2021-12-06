---
title: Defer
date: "2021-11-02T23:42:03.284Z"
description: 'Defer in Go?'
inHome: false
---

### Defer and stacking defers

Defer statements are used to defer the execution of a function call until the function that contains the `defer` statement completes execution.

Lets learn this with an example:

```go
package main

import "fmt"

func sample() {
	fmt.Println("Inside the sample()")
}
func main() {
	// sample() will be invoked only after executing the statements of main()
	defer sample()
	fmt.Println("Inside the main()")
}
```

The output will be

```
Inside the main()
Inside the sample()
```

Here execution of `sample()` is deferred until the execution of the enclosing function (`main()`) completes.

Stacking defer is using multiple defer statements. Suppose you have multiple defer statements inside a function. Go places all the deferred function calls in a stack, and once the enclosing function returns, the stacked functions are executed in the Last In First Out (LIFO) order.

You can see this in the below example.

Execute the below code

```go
package main

import "fmt"

func display(a int) {
	fmt.Println(a)
}
func main() {
	defer display(1)
	defer display(2)
	defer display(3)
	fmt.Println(4)
}
```

The output will be

```
4
3
2
1
```

Here the code inside the `main()` executes first, and then the deferred function calls are executed in the reverse order, i.e. 4, 3,2,1.
