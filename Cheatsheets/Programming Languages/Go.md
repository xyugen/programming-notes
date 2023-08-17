Variables and Data Types

```go
// Variable declaration
age := 30
name := "John"
salary := 50000.50
isStudent := true
```
## Control Structures

```go
// Conditional statements
if condition {
  // code
} else if anotherCondition {
  // code
} else {
  // code
}

// Loops
for i := 0; i < 5; i++ {
  // code
}

for index, value := range slice {
  // code
}
```

## Functions

```go
// Function declaration
func add(a, b int) int {
  return a + b
}
```

## Arrays and Slices

```go
numbers := []int{1, 2, 3, 4, 5}

// Access element
firstNumber := numbers[0]

// Loop through slice
for index, value := range numbers {
  // code
}
```

## Structs

```go
type Person struct {
  Name string
  Age  int
}

// Creating a struct
person := Person{Name: "John", Age: 30}
```

## Pointers

```go
x := 42
ptr := &x // Pointer to x

// Dereferencing pointer
value := *ptr
```

## Interfaces

```go
type Shape interface {
  Area() float64
}

type Circle struct {
  Radius float64
}

func (c Circle) Area() float64 {
  return 3.14 * c.Radius * c.Radius
}
```

## Goroutines

```go
func myFunction() {
  // code to run in the goroutine
}

func main() {
  go myFunction() // Create a new goroutine
  // code in main function
}
```

## Channels

```go
ch := make(chan int)

go func() {
  ch <- 42 // Sending data to the channel
}()

value := <-ch // Receiving data from the channel
```

## Error Handling

```go
result, err := someFunction()

if err != nil {
  // handle the error
} else {
  // use the result
}

```

## Packages

```go
import "fmt"

func main() {
  fmt.Println("Hello, world!")
}
```

## Defer

```go
func main() {
  defer fmt.Println("This will be printed last.")
  fmt.Println("This will be printed first.")
}
```

## Maps

```go
ages := map[string]int{
  "John": 30,
  "Jane": 25,
}

// Access value
johnsAge := ages["John"]

// Add/update value
ages["Alice"] = 28

// Delete value
delete(ages, "Jane")
```

## Constants

```go
const pi = 3.14
const (
  statusOK   = 200
  statusNotFound = 404
)
```

## JSON

```go
import "encoding/json"

type Person struct {
  Name string `json:"name"`
  Age  int    `json:"age"`
}

data := `{"name":"John","age":30}`
var person Person
json.Unmarshal([]byte(data), &person)
```

# Advanced

## Goroutines and Concurrency

```go
import (
  "fmt"
  "sync"
)

func main() {
  var wg sync.WaitGroup
  ch := make(chan int)

  for i := 0; i < 5; i++ {
    wg.Add(1)
    go func(i int) {
      defer wg.Done()
      // Perform work and send result to ch
      ch <- i * 2
    }(i)
  }

  go func() {
    wg.Wait()
    close(ch)
  }()

  for result := range ch {
    fmt.Println(result)
  }
}
```

## Channels and Select

```go
func main() {
  ch1 := make(chan int)
  ch2 := make(chan int)

  go func() {
    ch1 <- 42
  }()
  
  go func() {
    ch2 <- 100
  }()

  select {
  case val := <-ch1:
    fmt.Println("Received from ch1:", val)
  case val := <-ch2:
    fmt.Println("Received from ch2:", val)
  }
}
```

## Mutex and Locking

```go
var mu sync.Mutex
var balance = 1000

func withdraw(amount int) {
  mu.Lock()
  defer mu.Unlock()
  if balance >= amount {
    balance -= amount
  }
}

func main() {
  wg := sync.WaitGroup{}
  for i := 0; i < 5; i++ {
    wg.Add(1)
    go func() {
      defer wg.Done()
      withdraw(200)
    }()
  }
  wg.Wait()
  fmt.Println("Remaining balance:", balance)
}
```

## Context

```go
import (
  "context"
  "fmt"
  "time"
)

func main() {
  ctx, cancel := context.WithCancel(context.Background())
  defer cancel()

  go func() {
    select {
    case <-ctx.Done():
      fmt.Println("Goroutine canceled.")
      return
    case <-time.After(2 * time.Second):
      fmt.Println("Goroutine completed.")
    }
  }()

  time.Sleep(1 * time.Second)
  cancel() // Cancel the goroutine
  time.Sleep(1 * time.Second)
}
```

## Reflection

```go
import (
  "fmt"
  "reflect"
)

func main() {
  num := 42
  value := reflect.ValueOf(num)

  fmt.Println("Type:", value.Type())
  fmt.Println("Value:", value.Int())
}
```

## Custom Error Types

```go
type MyError struct {
  Message string
}

func (e *MyError) Error() string {
  return e.Message
}

func foo() error {
  return &MyError{"Something went wrong"}
}

func main() {
  err := foo()
  fmt.Println(err)
}
```

## Interfaces and Type Assertions

```go
type Shape interface {
  Area() float64
}

type Circle struct {
  Radius float64
}

func (c Circle) Area() float64 {
  return 3.14 * c.Radius * c.Radius
}

func main() {
  var s Shape = Circle{Radius: 5}
  circle, ok := s.(Circle)
  if ok {
    fmt.Println("Circle area:", circle.Area())
  } else {
    fmt.Println("Not a circle")
  }
}
```

## Custom Types

```go
type Shape interface {
  Area() float64
}

type Circle struct {
  Radius float64
}

func (c Circle) Area() float64 {
  return 3.14 * c.Radius * c.Radius
}

func main() {
  var s Shape = Circle{Radius: 5}
  circle, ok := s.(Circle)
  if ok {
    fmt.Println("Circle area:", circle.Area())
  } else {
    fmt.Println("Not a circle")
  }
}
```

## Context-Sensitive Logging

```go
import (
  "fmt"
  "log"
  "os"
)

func main() {
  f, err := os.OpenFile("logfile.log", os.O_APPEND|os.O_CREATE|os.O_WRONLY, 0644)
  if err != nil {
    log.Fatal(err)
  }
  defer f.Close()

  logger := log.New(f, "INFO: ", log.Ldate|log.Ltime|log.Lshortfile)
  logger.Println("Log entry")
}
```

## Function Composition

```go
func double(x int) int {
  return x * 2
}

func square(x int) int {
  return x * x
}

func main() {
  f := compose(square, double)
  result := f(5) // Equivalent to square(double(5))
  fmt.Println(result)
}

func compose(funcs ...func(int) int) func(int) int {
  return func(x int) int {
    for _, f := range funcs {
      x = f(x)
    }
    return x
  }
}
```

>[!Note]
>This advanced Go cheat-sheet covers more intricate features and concepts of the language. If you need further clarification or more advanced topics, feel free to ask!

#programming-languages 