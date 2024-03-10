# [_Pro Go_](../books/Pro_Go.pdf) Reading Notes

## Go Commands

Some useful `go` command arguments:

| Argument | Description |
|----------|-------------|
| `build` | Compiles source code in current directory, and generates an executable file. |
| `clean` | Removes the output produced by `go build`, including executables and temporary files created during the build. |
| `doc` | Generates documentation from source code. |
| `fmt` | Ensures consistent indentation and alignment in source code files. |
| `get` | Downloads and installs external packages. |
| `install` | Downloads packages; usually used to install tool packages. |
| `help` | Displays help information for other Go features. |
| `mod` | Creates and manages a Go module. |
| `run` | Builds and executes the source code without creating an executable output. |
| `test` | Executes unit tests. |
| `version` | Writes out the Go version number. |
| `vet` | Detects common problems in Go code. |

## Go Basics

### Basic Data Types

* Integer types:
    * Signed: `int` (sizes: `int8`, `int16`, `int32`, `int64`)
    * Unsigned: `uint` (sizes: `uint8`, `uint16`, `uint32`, `uint64`)
* Floating point types: `float32`, `float64`
* Complex types: `complex64`, `complex128`
* Boolean type: `bool`
* String type: `string`
* Unicode character type: `rune`

### Zero Values

* `int`: 0
* `uint`: 0
* `byte`: 0
* `float64`: 0
* `bool`: `false`
* `string`: `""`
* `rune`: 0

### Operators

* Arithmetic: `+`, `-`, `*`, `/`, `%`
* Comparison: `==`, `!=`, `<`, `>`, `<=`, `>=`
* Logical: `&&`, `||`, `!`
* Assignment: `=`, `%=`
* Self increment/decrement: `++`, `--`, `+=`, `-=`
* Bitwise: `&`, `|`, `^`, `&^`, `<<`, `>>`

### Integer Prefixes

* `0b`: Binary
* `0o`: Octal
* `0x`: Hexadecimal

### Flow Control

* Branch statements:
    * `if`, `else`
    * `switch`, `case`, `default`, `fallthrough`
* Loop statements:
    * `for`, `break`, `continue`
    * `range`
* Jumping statements:
    * `goto`

### Collection Types: Arrays, Slices, and Maps

* Data structures:
    * Array: Fixed number of values of the same type
    * Slice: Variable number of the values of the same type; or a view on an array
    * Map: Collection of key-value pairs
* Array operations:
    * Compare arrays: use comparison operators
    * Enumerate an array: use the `for` loop with `range` keyword
* Slice operations:
    * Allocate a slice: use the `make` function
    * Append to a slice: use the `append` function
    * Create a slice from an array: use a range
    * Copy elements to slice: use the `copy` function
    * Delete elements from a slice: use the `append` function with ranges that omit the elements to be deleted
    * Enumerate a slice: use the `for` loop with `range` keyword
    * Sort elements in a slice: use the `sort` package
    * Compare slices: use the `reflect` package
    * Obtain a pointer to an array underlying a slice: make an explicit conversion to convert the slice to an array whose length is less than or equal to the length of the slice
* Map operations:
    * Allocate a map: use the `make` function
    * Remove a key-value pair from a map: use the `delete` function
    * Enumerate the contents of a map: use the `for` loop with `range` keyword
* String operations:
    * Read byte values or characters: use the string as an array, or perform an explicit conversion to the `[]rune` type
    * Enumerate characters in a string: use the `for` loop with `range` keyword
    * Enumerate bytes in a string: make an explicit conversion to `byte[]`, then use the `for` loop with `range` keyword

### Type Assertion vs. Type Conversion

* Type Assertion:

    ```go
    // target: v
    // type: myInterface
    a := v.(myInterface)
    ```
* Type Conversion:

    ```go
    // value: b
    // target type: float64
    a := float64(b)
    ```

Difference between the **type assertion** and **type conversion**:

* **Type assertions** can be applied _only to interfaces_, and they are used to tell the compiler that an interface value has a _specific dynamic type_.
* **Type conversions** can be applied only to specific types, not interfaces, and only if the structure of those types is compatible, such as converting between struct types that have the same fields.