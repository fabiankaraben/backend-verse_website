---
title: What is Go?
date: "2021-11-01T22:12:03.284Z"
description: 'What is Go?'
inHome: false
---

Go (also known as Golang) is an open source programming language developed by Google. It is a statically-typed compiled language.

Go supports concurrent programming, i.e. it allows running multiple processes simultaneously. This is achieved using channels, goroutines, etc.

Go has garbage collection which itself does the memory management and allows the deferred execution of functions.

## Your First Go program

Create a folder called studyGo. We will create our go programs inside this folder.

Go files are created with the extension `.go`. 

You can run Go programs using the syntax:

```bash
go run <filename>
```

Create a file called first.go and add the below code into it and save

```go
package main
import ("fmt")

func main() {
    fmt.Println("Hello World! This is my first Go program\n")
}
```

Navigate to this folder in your terminal and run the program using the command:

```bash
go run first.go
```

You can see the output printing

```bash
Hello World! This is my first Go program
```

Now let's discuss the above program.

`package main` : Every go program should start with a package name. Go allows us to use packages in another go programs and hence supports code reusability. Execution of a go program begins with the code inside the package named main.

`import fmt` : imports the package fmt. This package implements the I/O functions.

`func main()` : This is the function from which program execution begins.

The main function should always be placed in the main package. 

Under the `main()`, You can write the code inside `{ }`.

`fmt.Println` : This will print the text on the screen by the Println function of fmt.
