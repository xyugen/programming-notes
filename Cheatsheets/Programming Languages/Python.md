## Variables and Data Types

```python
# Variable assignment
age = 30
name = "John"
salary = 50000.50
is_student = True
```

## Control Structures

```python
# Conditional statements
if condition:
    # code
elif another_condition:
    # code
else:
    # code

# Loops
for i in range(5):
    # code

while condition:
    # code
```

## Functions

```python
# Function definition
def greet(name):
    return "Hello, " + name + "!"

# Lambda function
add = lambda a, b: a + b

# Default argument
def print_info(name, age=25):
    print(name + " is " + str(age) + " years old.")
```

## Lists

```python
numbers = [1, 2, 3, 4, 5]

# Access element
first_number = numbers[0]

# Loop through list
for number in numbers:
    # code
```

## Dictionaries

```python
person = {
    "name": "John",
    "age": 30
}

# Access value
name = person["name"]

# Loop through dictionary
for key, value in person.items():
    # code
```

## Classes and Objects

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print("Hello, my name is " + self.name)

# Creating an object
person = Person("John", 30)
person.introduce()
```

## Inheritance and Polymorphism

```python
class Animal:
    def make_sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    def make_sound(self):
        print("Dog barks")
```

## Exception Handling

```python
try:
    # code that might raise an exception
except ExceptionType as e:
    # handle the exception
finally:
    # code that runs regardless of exceptions
```
## Modules and Packages

```python
# Importing module
import math

# Importing specific function
from math import sqrt

# Importing entire module
import my_module

# Importing module from package
from my_package import my_module
```

## File I/O

pythonCopy code

```python
# Reading from a file
with open("file.txt", "r") as file:
    content = file.read()

# Writing to a file
with open("output.txt", "w") as file:
    file.write("Hello, world!")
```

## Multithreading

```python
import threading

class MyThread(threading.Thread):
    def run(self):
        # code to run in the thread

# Creating and starting a thread
thread = MyThread()
thread.start()
```

## List Comprehensions

```python
numbers = [1, 2, 3, 4, 5]

squared = [x ** 2 for x in numbers]

filtered = [x for x in numbers if x % 2 == 0]
```

## Virtual Environments

```bash
# Creating a virtual environment
python -m venv myenv

# Activating the environment (Windows)
myenv\Scripts\activate

# Activating the environment (Linux/Mac)
source myenv/bin/activate

# Deactivating the environment
deactivate
```

# Advanced

## List Comprehensions and Generators

```python
# List comprehension
squared = [x ** 2 for x in range(1, 6)]

# Generator expression
squared_gen = (x ** 2 for x in range(1, 6))
```

## Decorators

```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

## Context Managers (with Statements)

```python
# Custom context manager
class MyContext:
    def __enter__(self):
        print("Entering the context")
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Exiting the context")

with MyContext() as context:
    print("Inside the context")
```

## Regular Expressions

```python
import re

# Search for a pattern
pattern = r"\d{2}-\d{2}-\d{4}"
text = "Date of birth: 25-12-1990"
match = re.search(pattern, text)

if match:
    print("Date:", match.group())
```

## Iterators and Iterables

```python
# Iterable
my_list = [1, 2, 3]

# Iterator
my_iterator = iter(my_list)
print(next(my_iterator))
```

## Coroutines and Asynchronous Programming

```python
async def my_coroutine():
    print("Start")
    await asyncio.sleep(1)
    print("End")

# Asynchronous execution
import asyncio
loop = asyncio.get_event_loop()
loop.run_until_complete(my_coroutine())
```

## Lambda Functions

```python
# Sorting a list of tuples by the second element
pairs = [(1, 'one'), (3, 'three'), (2, 'two')]
pairs.sort(key=lambda pair: pair[1])
```

## Namedtuples

```python
from collections import namedtuple

Point = namedtuple('Point', ['x', 'y'])
p = Point(1, 2)
print(p.x, p.y)
```

## Comprehensions with Conditional Logic

```python
# List comprehension with if-else
even_or_odd = ["even" if x % 2 == 0 else "odd" for x in range(1, 6)]

# Dictionary comprehension with condition
squared_dict = {x: x ** 2 for x in range(1, 6)}
```

## Unpacking and Packing

```python
# Unpacking a tuple
numbers = (1, 2, 3)
x, y, z = numbers

# Packing arguments
def my_function(*args):
    print(args)

my_function(1, 2, 3)
```

## Metaclasses

```python
class MyMeta(type):
    def __init__(cls, name, bases, attrs):
        print("Creating class:", name)
        super().__init__(name, bases, attrs)

class MyClass(metaclass=MyMeta):
    pass
```

## `__name__` and `__main__`

```python
def main():
    # Your main program logic here

if __name__ == "__main__":
    main()
```

## Type Annotations (PEP 484)

```python
def greeting(name: str) -> str:
    return "Hello, " + name
```

## Type Hinting (PEP 484 and 526)

```python
from typing import List, Tuple

def process_data(data: List[Tuple[str, int]]) -> List[str]:
    result = []
    for name, age in data:
        result.append(f"{name} is {age} years old.")
    return result
```

## Enumerations

```python
from enum import Enum

class Color(Enum):
    RED = 1
    GREEN = 2
    BLUE = 3

print(Color.RED)  # Output: Color.RED
```

>[!Note]
>This advanced cheat-sheet covers more complex Python concepts. Remember that these topics provide a deeper understanding of Python's capabilities.
