## Variables and Data Types

```java
// Variable declaration
int age = 30;
String name = "John";
double salary = 50000.50;
boolean isStudent = true;
```

## Control Structures

```java
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
```

## Functions

```java
// Method declaration
int add(int a, int b) {
  return a + b;
}

// Method overloading
double add(double a, double b) {
  return a + b;
}
```

## Arrays

```java
int[] numbers = { 1, 2, 3, 4, 5 };

// Access element
int firstNumber = numbers[0];

// Loop through array
for (int number : numbers) {
  // code
}
```

## Classes and Objects

```java
class Person {
  String name;
  int age;

  void introduce() {
    System.out.println("Hello, my name is " + name);
  }
}

// Creating an object
Person person = new Person();
person.name = "John";
person.age = 30;
person.introduce();
```

## Inheritance and Polymorphism

```java
class Animal {
  void makeSound() {
    System.out.println("Animal makes a sound");
  }
}

class Dog extends Animal {
  @Override
  void makeSound() {
    System.out.println("Dog barks");
  }
}
```

## Exception Handling

```java
try {
  // code that might throw an exception
} catch (ExceptionType e) {
  // handle the exception
} finally {
  // code that runs regardless of whether an exception was caught
}
```

## Interfaces and Abstract Classes

```java
interface Drawable {
  void draw();
}

abstract class Shape implements Drawable {
  // other methods and properties
}
```
## Packages and Imports

```java
// Importing a class
import java.util.ArrayList;

// Importing all classes from a package
import java.util.*;
```

## File I/O

```java
// Reading from a file
try (BufferedReader reader = new BufferedReader(new FileReader("file.txt"))) {
  String line;
  while ((line = reader.readLine()) != null) {
    // process the line
  }
} catch (IOException e) {
  // handle the exception
}

// Writing to a file
try (BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"))) {
  writer.write("Hello, world!");
} catch (IOException e) {
  // handle the exception
}
```
## Multithreading

```java
class MyThread extends Thread {
  public void run() {
    // code to run in the thread
  }
}

// Creating and starting a thread
MyThread thread = new MyThread();
thread.start();
```
## Generics

```java
class Box<T> {
  private T value;

  public void setValue(T value) {
    this.value = value;
  }

  public T getValue() {
    return value;
  }
}
```

# Advanced

### Object-Oriented Concepts

#### Encapsulation

```java
class Person {
  private String name;
  private int age;

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  // ... (similarly for other fields)
}
```

#### Inheritance

```java
class Parent {
  // ...
}

class Child extends Parent {
  // ...
}
```

#### Polymorphism

```java
interface Shape {
  void draw();
}

class Circle implements Shape {
  void draw() {
    // Draw a circle
  }
}

class Square implements Shape {
  void draw() {
    // Draw a square
  }
}
```

### Java Collections

#### ArrayList

```java
import java.util.ArrayList;

ArrayList<String> names = new ArrayList<>();
names.add("Alice");
names.add("Bob");
names.remove("Alice");
```

#### HashMap

```java
import java.util.HashMap;

HashMap<String, Integer> ages = new HashMap<>();
ages.put("Alice", 25);
ages.put("Bob", 30);
int age = ages.get("Alice");
```

#### Filtering and Mapping

```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
List<Integer> evenSquares = numbers.stream()
                                   .filter(n -> n % 2 == 0)
                                   .map(n -> n * n)
                                   .collect(Collectors.toList());
```

#### Sorting

```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
List<String> sortedNames = names.stream()
                               .sorted()
                               .collect(Collectors.toList());
```

### Java Exceptions

```java
try {
  // code that might throw an exception
} catch (ExceptionType e) {
  // handle the exception
} finally {
  // code that runs regardless of whether an exception was caught
}
```

### Java Threads

#### Runnable Interface

```java
class MyRunnable implements Runnable {
  public void run() {
    // code to run in the thread
  }
}

Thread thread = new Thread(new MyRunnable());
thread.start();
```

#### Synchronization

```java
class Counter {
  private int count = 0;

  public synchronized void increment() {
    count++;
  }
}
```

### Java Generics

```java
class Box<T> {
  private T value;

  public void setValue(T value) {
    this.value = value;
  }

  public T getValue() {
    return value;
  }
}
```

### Java File I/O

#### Reading from a File

```java
try (BufferedReader reader = new BufferedReader(new FileReader("file.txt"))) {
  String line;
  while ((line = reader.readLine()) != null) {
    // process the line
  }
} catch (IOException e) {
  // handle the exception
}
```

#### Writing to a File

```java
try (BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"))) {
  writer.write("Hello, world!");
} catch (IOException e) {
  // handle the exception
}
```

### Java Enumerations

```java
enum Day {
  SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}

Day today = Day.MONDAY;
```

>[!Note]
>Remember that this cheat-sheet covers only some of the key concepts in Java.

#programming-languages