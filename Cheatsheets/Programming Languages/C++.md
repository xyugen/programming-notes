# Variables and Data Types

```cpp
// Variable declaration
int age = 30;
double salary = 50000.50;
char grade = 'A';
bool isStudent = true;
```

## Control Structures

```cpp
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

```cpp
// Function declaration
int add(int a, int b) {
  return a + b;
}

// Function overloading
double add(double a, double b) {
  return a + b;
}
```

## Arrays

```cpp
int numbers[] = { 1, 2, 3, 4, 5 };

// Access element
int firstNumber = numbers[0];

// Loop through array
for (int i = 0; i < 5; i++) {
  // code
}
```
## Classes and Objects

```cpp
class Person {
public:
  string name;
  int age;

  void introduce() {
    cout << "Hello, my name is " << name << endl;
  }
};

// Creating an object
Person person;
person.name = "John";
person.age = 30;
person.introduce();
```

## Inheritance and Polymorphism

```cpp
class Animal {
public:
  virtual void makeSound() {
    cout << "Animal makes a sound" << endl;
  }
};

class Dog : public Animal {
public:
  void makeSound() override {
    cout << "Dog barks" << endl;
  }
};
```

## Exception Handling

```cpp
try {
  // code that might throw an exception
} catch (ExceptionType e) {
  // handle the exception
} finally {
  // code that runs regardless of whether an exception was caught
}
```

## Templates

```cpp
template <typename T>
T add(T a, T b) {
  return a + b;
}

int result = add<int>(5, 10);
```

## Standard Template Library (STL)

```cpp
#include <vector>
#include <map>

// Vector
vector<int> numbers = { 1, 2, 3, 4, 5 };

// Map
map<string, int> ages;
ages["John"] = 30;
```

## File I/O

```cpp
// Reading from a file
ifstream inFile("input.txt");
string line;
while (getline(inFile, line)) {
  // process the line
}

// Writing to a file
ofstream outFile("output.txt");
outFile << "Hello, world!" << endl;
```

## Multithreading

```cpp
#include <thread>

void myFunction() {
  // code to run in the thread
}

int main() {
  thread t(myFunction);
  t.join();
  return 0;
}
```

## Smart Pointers

```cpp
#include <memory>

// Creating smart pointers
std::unique_ptr<int> myUniquePtr(new int);
std::shared_ptr<int> mySharedPtr = std::make_shared<int>();

// Creating shared_ptr
std::shared_ptr<int> sharedPtr = std::make_shared<int>(42);

// Creating unique_ptr
std::unique_ptr<double> uniquePtr = std::make_unique<double>(3.14);

// Creating weak_ptr
std::weak_ptr<int> weakPtr = sharedPtr;
```

# Advanced

## Lambda Expressions

```cpp
// Lambda function
auto sum = [](int a, int b) -> int {
  return a + b;
};

int result = sum(5, 10);
```

## Standard Template Library (STL) Algorithms

```cpp
#include <algorithm>
#include <vector>

std::vector<int> numbers = { 3, 1, 4, 1, 5, 9, 2, 6, 5, 3 };

// Sorting
std::sort(numbers.begin(), numbers.end());

// Finding element
auto it = std::find(numbers.begin(), numbers.end(), 5);

// Transforming
std::transform(numbers.begin(), numbers.end(), numbers.begin(), [](int n) {
  return n * n;
});
```

## Custom Iterators

```cpp
class MyIterator : public std::iterator<std::input_iterator_tag, int> {
  // iterator implementation
};
```

## Move Semantics

```cpp
// Move constructor
MyClass(MyClass&& other) noexcept {
  // move data from 'other' to 'this'
}

// Move assignment operator
MyClass& operator=(MyClass&& other) noexcept {
  if (this != &other) {
    // move data from 'other' to 'this'
  }
  return *this;
}
```

## CRTP (Curiously Recurring Template Pattern)

```cpp
template <typename Derived>
class Base {
  // implementation using methods from Derived
};

class Derived : public Base<Derived> {
  // implementation
};
```

## RAII (Resource Acquisition Is Initialization)

```cpp
class FileHandler {
public:
  FileHandler(const std::string& filename) {
    file.open(filename);
  }

  ~FileHandler() {
    if (file.is_open()) {
      file.close();
    }
  }

private:
  std::ofstream file;
};
```

## Variadic Templates

```cpp
template <typename T>
void print(T value) {
  std::cout << value << std::endl;
}

template <typename T, typename... Args>
void print(T value, Args... args) {
  std::cout << value << " ";
  print(args...);
}
```

## SFINAE (Substitution Failure Is Not An Error)

```cpp
template <typename T>
typename std::enable_if<std::is_integral<T>::value, T>::type
square(T value) {
  return value * value;
}
```

## CRTP for Mixins

```cpp
template <typename Derived>
class Printable {
public:
  void print() const {
    static_cast<const Derived*>(this)->printImpl();
  }
};

class MyClass : public Printable<MyClass> {
public:
  void printImpl() const {
    // print implementation
  }
};
```

## C++20 Concepts

```cpp
template <typename T>
concept Integral = std::is_integral<T>::value;

template <Integral T>
T square(T value) {
  return value * value;
}
```

>[!Note]
>This advanced C++ cheat-sheet covers more intricate features and concepts of the language.

