---
title:  "Basic Types"
tags: go basic types
---

Here are all basic types.

| Type | Size in bytes |
| --- | --- |
| bool | 1 |
| rune | 4 |
| int | 8 |
| int8 | 1 |
| int16 | 2 |
| int32 | 4 |
| int64 | 8 |
| uint | 8 |
| uint8 | 1 |
| uint16 | 2 |
| uint32 | 4 |
| uint64 | 8 |
| uintptr | 8 |
| byte | 1 |
| float32 | 4 |
| float64 | 8 |
| complex64 | 8 |
| complex128 | 16 |

<p class="code-link" markdown='1'>
	[See in playground](https://play.golang.org/p/gjkn7F3T9zk){:target="_blank"}
</p>
```go
package main

import (
	"fmt"
	"reflect"
)

func main() {
	values := []interface{}{
		true,            // should print "true bool 1"
		'f',             // should print "102 int32 4"
		int(102),        // should print "102 int 8"
		int8(102),       // should print "102 int8 1"
		int16(102),      // should print "102 int16 2"
		int32(102),      // should print "102 int32 4"
		int64(102),      // should print "102 int64 8"
		uint(102),       // should print "102 uint 8"
		uint8(102),      // should print "102 uint8 1"
		uint16(102),     // should print "102 uint16 2"
		uint32(102),     // should print "102 uint32 4"
		uint64(102),     // should print "102 uint64 8"
		uintptr(102),    // should print "102 uintptr 8"
		byte(102),       // should print "102 uint8 1"
		float32(102),    // should print "102 float32 4"
		float64(102),    // should print "102 float64 8"
		complex64(102),  // should print "(102+0i) complex64 8"
		complex128(102), // should print "(102+0i) complex128 16"
	}
	for _, value := range values {
		fmt.Printf("%v %T %d\n", value, value, reflect.TypeOf(value).Size())
	}
}
```

Using the package `reflect` we can get many interesting insights about each type in Go. Also we are using the type `[]interface{}` which is a mixture of `slices` of `empty interfaces` which I hope to cover in the future.

*Note* `byte` is a builtin alias for `uint8` and `rune` an alias for `int32`.
