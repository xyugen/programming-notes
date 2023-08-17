## Variables and Data Types

```csharp
// Variable declaration
int age = 30;
string name = "John";
double salary = 50000.50;
bool isStudent = true;

// Implicit typing with 'var'
var age = 30;
var name = "John";

// Nullable value types
int? nullableAge = null;

// Constants
const double Pi = 3.14159;
```

## Control Structures

```csharp
// Conditional statements
if (condition) {
  // code
} else if (anotherCondition) {
  // code
} else {
  // code
}

// Loops
for (int i = 0; i < 5; i++) {
  // code
}

while (condition) {
  // code
}

// Switch statement
switch (variable) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // code
        break;
}
```

## Functions

```csharp
// Method declaration
int Add(int a, int b) {
  return a + b;
}

// Optional parameters
void Greet(string name, string greeting = "Hello") {
    Console.WriteLine($"{greeting}, {name}!");
}
Greet("John"); // Prints "Hello, John!"

// Named arguments
Greet(greeting: "Hi", name: "Alice"); // Prints "Hi, Alice!"
```

## Arrays

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };

// Access element
int firstNumber = numbers[0];

// Loop through array
foreach (int number in numbers) {
  // code
}
```

## Classes and Objects

```csharp
class Person {
  public string Name { get; set; }
  public int Age { get; set; }

  public void Introduce() {
    Console.WriteLine($"Hello, my name is {Name}");
  }
}

// Creating an object
Person person = new Person();
person.Name = "John";
person.Age = 30;
person.Introduce();

// Constructors
class Person {
    public Person(string name, int age) {
        Name = name;
        Age = age;
    }
}

// Properties with get and set accessors
public string Name { get; set; }

// Auto-implemented properties
public int Age { get; set; } = 25;
```

## Inheritance and Polymorphism

```csharp
class Animal {
  public virtual void MakeSound() {
    Console.WriteLine("Animal makes a sound");
  }
}

class Dog : Animal {
  public override void MakeSound() {
    Console.WriteLine("Dog barks");
  }
}

// Abstract methods and classes
abstract class Shape {
    public abstract double Area();
}

// Sealed classes
sealed class FinalClass {
    // code
}
```

## Exception Handling

```csharp
try {
  // code that might throw an exception
} catch (ExceptionType e) {
  // handle the exception
} finally {
  // code that runs regardless of whether an exception was caught
}
```

## Interfaces and Abstract Classes

```csharp
interface IDrawable {
  void Draw();
}

abstract class Shape : IDrawable {
  // other methods and properties
}

// Explicit interface implementation
class MyClass : IInterface {
    void IInterface.Method() {
        // code
    }
}
```

## Namespaces and Using Directives

```csharp
// Using a namespace
using System;

// Using a specific class from a namespace
using System.Collections.Generic;

// Aliasing namespaces
using Project = MyCompany.Project;

// Global namespace alias
global::System.Console.WriteLine("Global namespace");
```

## File I/O

```csharp
// Reading from a file
using (StreamReader reader = new StreamReader("file.txt")) {
  string line;
  while ((line = reader.ReadLine()) != null) {
    // process the line
  }
}

// Writing to a file
using (StreamWriter writer = new StreamWriter("output.txt")) {
  writer.WriteLine("Hello, world!");
}

// Reading all lines from a file
string[] lines = File.ReadAllLines("file.txt");

// Appending to a file
File.AppendAllText("output.txt", "Appended text");
```

## Multithreading

```csharp
class MyThread {
  public void Run() {
    // code to run in the thread
  }
}

// Creating and starting a thread
Thread thread = new Thread(new MyThread().Run);
thread.Start();

// Asynchronous programming
async Task MyAsyncMethod() {
    await Task.Delay(1000);
    Console.WriteLine("Async method completed.");
}
```

## Generics

```csharp
class Box<T> {
  private T value;

  public void SetValue(T value) {
    this.value = value;
  }

  public T GetValue() {
    return value;
  }
}

// Constraints
class GenericClass<T> where T : class {
    // code
}

// Delegates and Generic methods
delegate T GenericDelegate<T>(T arg);

T MyMethod<T>(T arg) {
    // code
}
```

>[!Note]
>Please note that this cheat-sheet covers only some of the key concepts in C#.

#programming-languages