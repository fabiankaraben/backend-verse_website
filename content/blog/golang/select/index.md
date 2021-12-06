---
title: Select
date: "2021-11-03T23:02:03.284Z"
description: 'Select in Go?'
inHome: false
---

Select can be viewed as a switch statement which works on channels. Here the case statements will be a channel operation. Usually, each case statements will be read attempt from the channel. 

When any of the cases is ready(the channel is read), then the statement associated with that case is executed. If multiple cases are ready, it will choose a random one. 

You can have a default case which is executed if none of the cases is ready.

Let's see the below code

```go
package main

import (
	"fmt"
	"time"
)

// Push data to channel with a 4 second delay
func data1(ch chan string) {
	time.Sleep(4 * time.Second)
	ch <- "from data1()"
}

// Push data to channel with a 2 second delay
func data2(ch chan string) {
	time.Sleep(2 * time.Second)
	ch <- "from data2()"
}
func main() {
	// Creating channel variables for transporting string values
	chan1 := make(chan string)
	chan2 := make(chan string) // Invoking the subroutines with channel variables
	go data1(chan1)
	go data2(chan2)
	// Both case statements wait for data in the chan1 or chan2.
	// chan2 gets data first since the delay is only 2 sec in data2().
	// So the second case will execute and exits the select block
	select {
	case x := <-chan1:
		fmt.Println(x)
	case y := <-chan2:
		fmt.Println(y)
	}
}
```

Executing the above program will give the output:

```
from data2()
```

Here the select statement waits for data to be available in any of the channels. The data2() adds data to the channel after a sleep of 2 seconds which will cause the second case to execute.

Add a default case to the select in the same program and see the output.

Here, on reaching select block, if no case is having data ready on the channel, it will execute the default block without waiting for data to be available on any channel.

```go
package main

import (
	"fmt"
	"time"
)

// Push data to channel with a 4 second delay
func data1(ch chan string) {
	time.Sleep(4 * time.Second)
	ch <- "from data1()"
}

// Push data to channel with a 2 second delay
func data2(ch chan string) {
	time.Sleep(2 * time.Second)
	ch <- "from data2()"
}
func main() {
	// Creating channel variables for transporting string values
	chan1 := make(chan string)
	chan2 := make(chan string)
	// Invoking the subroutines with channel variables
	go data1(chan1)
	go data2(chan2)
	// Both case statements check for data in chan1 or chan2.
	// But data is not available (both routines have a delay of 2 and 4 sec)
	// So the default block will be executed without waiting for data in channels.
	select {
	case x := <-chan1:
		fmt.Println(x)
	case y := <-chan2:
		fmt.Println(y)
	default:
		fmt.Println("Default case executed")
	}
}
```

This program will give the output:

```
Default case executed
```

This is because when the select block reached, no channel had data for reading. So, the default case is executed.

