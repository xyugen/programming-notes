# Basics
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

# String and Math Classes
#### String Class Methods
The `String` class in Java provides a variety of methods for manipulating and working with strings. Here are some commonly used methods:

- `length()`: Returns the length (number of characters) of the string.
- `charAt(int index)`: Returns the character at the specified index.
- `substring(int beginIndex, int endIndex)`: Returns a new string that is a substring of the original string.
- `concat(String str)`: Concatenates the specified string to the end of the original string.
- `toUpperCase()` / `toLowerCase()`: Converts the string to uppercase or lowercase.
- `indexOf(String str)`: Returns the index of the first occurrence of the specified substring.
- `replace(char oldChar, char newChar)`: Replaces all occurrences of `oldChar` with `newChar`.
- `split(String regex)`: Splits the string into an array of substrings based on the given regular expression.
- `trim()`: Removes leading and trailing whitespaces from the string.

#### Math Class Methods
The `Math` class in Java provides various static methods for performing mathematical operations. Some commonly used methods include:

- `abs(int a)` / `abs(double a)`: Returns the absolute value of a number.
- `max(int a, int b)` / `max(double a, double b)`: Returns the larger of the two given numbers.
- `min(int a, int b)` / `min(double a, double b)`: Returns the smaller of the two given numbers.
- `pow(double base, double exponent)`: Returns the value of `base` raised to the power of `exponent`.
- `sqrt(double a)`: Returns the square root of a non-negative number.
- `round(float a)` / `round(double a)`: Returns the closest integer to the given number.
- `random()`: Returns a random double value between 0 (inclusive) and 1 (exclusive).
### Example Usage
```java
public class StringAndMathExample {
    public static void main(String[] args) {
        // String methods
        String text = "Hello, Java Programming";
        System.out.println("Length: " + text.length());
        System.out.println("Character at index 7: " + text.charAt(7));
        System.out.println("Substring: " + text.substring(7, 11));
        System.out.println("Concatenated: " + text.concat(" is fun!"));
        System.out.println("Uppercase: " + text.toUpperCase());
        System.out.println("Index of 'Java': " + text.indexOf("Java"));
        System.out.println("Replaced: " + text.replace('o', 'O'));
        System.out.println("Split: " + Arrays.toString(text.split("\\s+")));
        System.out.println("Trimmed: " + text.trim());

        // Math methods
        int num1 = -5, num2 = 10;
        System.out.println("Absolute value: " + Math.abs(num1));
        System.out.println("Max value: " + Math.max(num1, num2));
        System.out.println("Min value: " + Math.min(num1, num2));
        System.out.println("2 raised to the power of 3: " + Math.pow(2, 3));
        System.out.println("Square root of 25: " + Math.sqrt(25));
        System.out.println("Rounded value: " + Math.round(7.75));
        System.out.println("Random value: " + Math.random());
    }
}
```

>[!Note]
>Remember to import the required classes (`java.util.Arrays` for the array-related method) at the beginning of your Java file.

# Packages and Imports
#### Packages
- Packages are used to organize and group related classes and interfaces together.
- They help prevent naming conflicts and provide a hierarchical structure to the codebase.

##### Creating Packages
```java
package com.example.myapp; // Declare package at the beginning of the file

public class MyClass {
    // Class code here
}
```
##### Accessing Classes from Packages
```java
import com.example.myapp.MyClass; // Import specific class from package

public class Main {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        // Use obj and other classes from the package
    }
}
```
#### Imports
- `import` statement is used to bring classes and interfaces from other packages into the current code.
- It helps avoid fully qualified class names.
##### Import Types
```java
import java.util.*; // Import all classes from java.util package
import java.util.ArrayList; // Import only ArrayList from java.util package
```
#### Default Package
- Classes without a package declaration are part of the default package.
- It's recommended to use packages to avoid naming conflicts and organize code.

#### Classpath
- The classpath is a list of directories and JAR files that Java uses to search for classes.
- Set using `-classpath` or `-cp` option or the `CLASSPATH` environment variable.
##### Command Line
```bash
java -classpath /path/to/classes:/path/to/libs/* MyMainClass
```
#### Jar Files
- JAR (Java Archive) files bundle multiple classes, resources, and metadata into one file.
- Create: `jar cf MyJar.jar MyClass.class OtherClass.class`
- Execute: `java -cp MyJar.jar MyMainClass`

#### Package Naming Conventions
- Packages use reverse domain naming convention, e.g., `com.example.myapp`.
- Use lowercase for package names, e.g., `com.example.myapp`.
### 9. Interfaces and Inheritance
#### Interfaces
An interface in Java is a blueprint for a class. It defines a set of method signatures that a class implementing the interface must provide. Interfaces enable multiple classes to share common method signatures without inheriting from a common superclass. Some key points about interfaces:
- Declare an interface using the `interface` keyword.
- All methods in an interface are implicitly `public` and `abstract`. They cannot have method bodies.
- Classes implement interfaces using the `implements` keyword.

```java
interface Drawable {
    void draw();
}

class Circle implements Drawable {
    public void draw() {
        // Implementation for drawing a circle
    }
}
```
#### Inheritance
Inheritance is a fundamental concept in OOP that allows a class (subclass or derived class) to inherit the attributes and methods of another class (superclass or base class). It promotes code reuse and hierarchical organization of classes.
- Use the `extends` keyword to create a subclass that inherits from a superclass.
- Subclasses can access public and protected members of the superclass.
- Java supports single inheritance (a subclass can only inherit from one superclass), but multiple interfaces can be implemented.

```java
class Animal {
    void eat() {
        System.out.println("Animal is eating.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking.");
    }
}
```
#### Polymorphism
Polymorphism allows objects of different classes to be treated as objects of a common superclass. This promotes flexibility and code reusability.
- Polymorphism is achieved through method overriding (subclass provides a specific implementation of a method from the superclass).
- The `@Override` annotation indicates that a method in a subclass is intended to override a method in the superclass.
- Polymorphism is particularly useful when dealing with collections of objects.

```java
class Shape {
    void draw() {
        System.out.println("Drawing a shape.");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle.");
    }
}

class Square extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a square.");
    }
}
```
#### Abstract Classes
An abstract class cannot be instantiated and is often used as a base for other classes. It can contain both abstract (without method body) and concrete methods.
- Declare an abstract class using the `abstract` keyword.
- Abstract methods are declared without a method body and must be overridden by subclasses.

```java
abstract class Shape {
    abstract void draw(); // Abstract method

    void resize() {
        System.out.println("Resizing the shape.");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle.");
    }
}
```
#### Super Keyword
The `super` keyword is used to refer to the superclass's members (methods, fields, constructors) within a subclass.
- It is used to call a superclass constructor and access overridden methods or fields.

```java
class Parent {
    void display() {
        System.out.println("Parent class method.");
    }
}

class Child extends Parent {
    @Override
    void display() {
        super.display(); // Call parent class method
        System.out.println("Child class method.");
    }
}
```

#programming-languages