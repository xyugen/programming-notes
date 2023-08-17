# Variables and Data Types

```rust
// Variable declaration
let age = 30;
let name = "John";
let salary = 50000.50;
let is_student = true;
```
## Control Structures

```rust
// Conditional statements
if condition {
    // code
} else if another_condition {
    // code
} else {
    // code
}

// Loops
for i in 0..5 {
    // code
}

while condition {
    // code
}
```

## Functions

```rust
// Ownership
let s1 = String::from("hello");
let s2 = s1;

// Borrowing
fn calculate_length(s: &String) -> usize {
    s.len()
}
```

## Ownership and Borrowing

```rust
// Ownership
let s1 = String::from("hello");
let s2 = s1;

// Borrowing
fn calculate_length(s: &String) -> usize {
    s.len()
}
```

## Structs and Enums

```rust
// Struct
struct Person {
    name: String,
    age: i32,
}

// Enum
enum Color {
    Red,
    Green,
    Blue,
}
```

## Pattern Matching

```rust
match value {
    Pattern1 => { /* code */ },
    Pattern2 => { /* code */ },
    _ => { /* default code */ },
}
```

## Error Handling

```rust
fn do_something() -> Result<(), MyError> {
    if something_went_wrong {
        return Err(MyError);
    }
    Ok(())
}
```

## Traits

```rust
trait Printable {
    fn print(&self);
}

struct Person {
    name: String,
}

impl Printable for Person {
    fn print(&self) {
        println!("Name: {}", self.name);
    }
}
```

## Lifetimes

```rust
// Function with lifetimes
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}
```

## Option and Result

```rust
// Option
let maybe_name: Option<String> = Some("John".to_string());

// Result
fn do_something() -> Result<(), MyError> {
    // code
}

```

## Closures

```rust
let add = |a, b| a + b;
let result = add(5, 10);
```

## Concurrency and Threads

```rust
use std::thread;

let handle = thread::spawn(|| {
    // code to run in the thread
});

handle.join().unwrap();
```

## Ownership in Threads

```rust
use std::thread;

let data = vec![1, 2, 3];
let handle = thread::spawn(move || {
    // code that uses 'data'
});
```

## Smart Pointers

```rust
use std::rc::Rc;
use std::sync::Arc;

// Reference Counting (Rc)
let rc = Rc::new(42);

// Atomic Reference Counting (Arc)
let arc = Arc::new(42);
```

# Advanced

## Lifetimes and Borrowing

```rust
// Lifetime annotations
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}

// Mutable references
let mut s = String::from("hello");
let r1 = &mut s;
let r2 = &mut s; // Error: cannot borrow `s` mutably more than once at a time
```

## Traits and Generics

```rust
// Generic function
fn print<T: std::fmt::Debug>(value: T) {
    println!("{:?}", value);
}

// Trait bounds
fn process<T: Printable + Clone>(item: T) {
    // code
}
```

## Advanced Error Handling

```rust
// Custom error type
enum MyError {
    Io(std::io::Error),
    Parse(std::num::ParseIntError),
}

// Implementing From trait
impl From<std::io::Error> for MyError {
    fn from(error: std::io::Error) -> Self {
        MyError::Io(error)
    }
}
```

## Concurrency and Multithreading

```rust
use std::sync::{Mutex, Arc};
use std::thread;

// Mutex for thread synchronization
let counter = Arc::new(Mutex::new(0));

for _ in 0..10 {
    let counter = Arc::clone(&counter);
    thread::spawn(move || {
        let mut num = counter.lock().unwrap();
        *num += 1;
    });
}

// Barrier for synchronization
let barrier = Arc::new(Barrier::new(4));

for _ in 0..4 {
    let barrier = Arc::clone(&barrier);
    thread::spawn(move || {
        // code before barrier
        barrier.wait();
        // code after barrier
    });
}
```
## Advanced Lifetimes

```rust
// 'static lifetime
fn global_string() -> &'static str {
    "hello"
}
```

## Unsafe Rust

```rust
// Unsafe function
unsafe fn dangerous_function() {
    // code
}

// Using unsafe block
let raw_data = [0u8, 1u8, 2u8];
let value = unsafe { std::mem::transmute::<[u8; 3], i32>(raw_data) };
```

## Advanced Patterns

```rust
// Destructuring enums
match my_enum {
    MyEnum::Variant1 { field } => { /* code */ },
    MyEnum::Variant2 { field1, field2 } => { /* code */ },
}

// Destructuring tuples
let (x, y) = (5, 10);
```

## Macros

```rust
// Defining a macro
macro_rules! my_macro {
    ($x:expr) => {
        println!("Value: {}", $x);
    };
}

// Using the macro
my_macro!(42);
```

## Traits for Operator Overloading

```rust
trait Container {
    type Item;
    
    fn get(&self, index: usize) -> Self::Item;
}

struct MyContainer {
    items: Vec<i32>,
}

impl Container for MyContainer {
    type Item = i32;
    
    fn get(&self, index: usize) -> Self::Item {
        self.items[index]
    }
}
```
## Associated Types

```rust
trait Container {
    type Item;
    
    fn get(&self, index: usize) -> Self::Item;
}

struct MyContainer {
    items: Vec<i32>,
}

impl Container for MyContainer {
    type Item = i32;
    
    fn get(&self, index: usize) -> Self::Item {
        self.items[index]
    }
}
```

>[!Note]
>This advanced Rust cheat-sheet covers intricate features and concepts of the language.

#programming-languages 