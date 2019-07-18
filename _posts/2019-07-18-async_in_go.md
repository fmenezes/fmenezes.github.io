---
title:  "Asynchronous Code in Go"
tags: go async
---

One of the fundamental concepts of [Go](http://golang.org){:target="_blank"} is writing asynchronous code and this is accomplished using `go` command.

```go
package main

import (
	"fmt"
	"time"
)

func main() {
	syncCode()

	go asyncCode()

	time.Sleep(time.Second)
}

func syncCode() {
  fmt.Println("synchronous code")
}

func asyncCode() {
	fmt.Println("asynchronous code")
}

```

The first interesting line is this one ```syncCode()``` this code runs immediately synchronously.

Next statement is ```go asyncCode()``` this command `go` is used to make the execution run in another thread.

Last statement ```time.Sleep(time.Second)``` is simply a hack to wait 1 second so the asynchronous code runs before exiting the process (in Go the main thread finishes last statement runs in function `main`).
