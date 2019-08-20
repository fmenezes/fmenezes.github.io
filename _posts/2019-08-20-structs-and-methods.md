---
title:  "Structures and methods"
tags: go struct
---

Structs can have methods.

<p class="code-link" markdown='1'>
	[See in playground](https://play.golang.org/p/oHYs0HaDukz){:target="_blank"}
</p>
```go
package main

import "fmt"

type Person struct {
	name string
	age  int
}

func (p Person) Print() {
	fmt.Printf("%v is %v years old\n", p.name, p.age)
}

func main() {
	a := Person{
		name: "Alan",
		age:  25,
	}
	a.Print() // result should be "Alan is 25 years old"
	a.name = "Bryan"
	a.Print() // result should be "Bryan is 25 years old"
}
```

Check `func (p Person) Print()` this contains what is called a *method receiver*.

Also you can use a method receiver with a pointer, the difference here is with a pointer you can update contents of a struct.

<p class="code-link" markdown='1'>
	[See in playground](https://play.golang.org/p/zHoCNds7XTR)
</p>
```go
package main

import "fmt"

type Person struct {
	name string
	age  int
}

func (p Person) Print() {
	fmt.Printf("%v is %v years old\n", p.name, p.age)
}

func (p *Person) SetName(name string) {
	p.name = name
}

func main() {
	a := Person{
		name: "Alan",
		age:  25,
	}
	a.Print() // result should be "Alan is 25 years old"
	a.SetName("Bryan")
	a.Print() // result should be "Bryan is 25 years old"
}
```
