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
```

>[!Note]
>Please note that this cheat-sheet covers only some of the key concepts in C++.
