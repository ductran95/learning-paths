# Golang basic syntax

> This section covers basic syntax of Go

# Table of Contents
- [Golang basic syntax](#golang-basic-syntax)
- [Table of Contents](#table-of-contents)
  - [Package](#package)
  - [Import](#import)
  - [Export](#export)
  - [Basic type](#basic-type)
  - [Function](#function)

## Package

- Package equivalent to namespace in C#
- Program has one or many packages
- Program start with func `main` in package `main`

## Import

- Import equivalent to `using` in C#
- To use things from other packages
- Have 2 style
  + Import multiple
    ```go
    import (
    	"fmt"
    	"math"
    )
    ```

  + Import single
    ```go
    import "fmt"
    import "math"
    ```

## Export

- A name (function, const ...) need to be exported to used in other packages
- Go has no equivalent scopes to C# (public, internal, protected, private), only exported and unexported
- Name start with capital letter => exported
- Otherwise => not exported

## Basic type

```go
bool
string
int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr
byte // alias for uint8
rune // alias for int32
     // represents a Unicode code point
float32 float64
complex64 complex128
```

- `int`, `uint`, and `uintptr` are 32 bit in 32-bit system, and 64 bit in 64-bit system
- Zero value: `0`, `false` and `""`
- Type conversion (casting): use `T(v)`
  ```go
  var i int = 42
  var f float64 = float64(i)
  ```
- Type inference: 
  + Auto detect type from value
  ```go
  var i int
  j := i // j is an int
  ```
  
  + Auto detect from numeric constant
  ```go
  i := 42           // int
  f := 3.142        // float64
  g := 0.867 + 0.5i // complex128
  ```

## Function

```go
func add(x int, y int) int {
	return x + y
}
```

- Argument: zero or many
  + Type after variable name
    ```go
    x int, y int
    ```

  + Omit type: when two or more arguments have same type
    ```go
    x, y int
    ```
  
- Result: 