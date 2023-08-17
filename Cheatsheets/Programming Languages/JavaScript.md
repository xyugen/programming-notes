## Variables and Data Types

```js
// Variable declaration
let name = "John";
const age = 30;

// Data types
let num = 42; // Number
let str = "Hello"; // String
let bool = true; // Boolean
let arr = [1, 2, 3]; // Array
let obj = { key: "value" }; // Object
```

## Control Structures

```js
// Conditional statements
if (condition) {
  // code
} else if (anotherCondition) {
  // code
} else {
  // code
}

// Loops
for (let i = 0; i < 5; i++) {
  // code
}

while (condition) {
  // code
}
```

## Functions

```js
// Function declaration
function greet(name) {
  return "Hello, " + name + "!";
}

// Arrow function
const add = (a, b) => a + b;

// Callback function
function doSomething(callback) {
  // code
  callback();
}
```

## Arrays

```js
let fruits = ["apple", "banana", "orange"];

// Access element
let firstFruit = fruits[0];

// Add element
fruits.push("grape");

// Remove element
fruits.pop();

// Loop through array
for (let fruit of fruits) {
  console.log(fruit);
}
```

## Objects

```js
let person = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
};

// Access property
let firstName = person.firstName;

// Add property
person.email = "john@example.com";

// Loop through object
for (let key in person) {
  console.log(key + ": " + person[key]);
}
```

## Promises and Async/Await

```js
// Promises
const fetchData = () => {
  return new Promise((resolve, reject) => {
    // Asynchronous operation
    if (dataIsAvailable) {
      resolve(data);
    } else {
      reject("Data not available");
    }
  });
};

// Async/Await
async function getData() {
  try {
    let result = await fetchData();
    console.log(result);
  } catch (error) {
    console.error(error);
  }
}
```

## Modules (ES6)

```js
// Exporting module
export const add = (a, b) => a + b;

// Importing module
import { add } from "./math";
```

## DOM Manipulation

```js
// Selecting element
const element = document.getElementById("myElement");

// Event listener
element.addEventListener("click", () => {
  // code
});

// Changing content
element.innerHTML = "New content";
```
## Error Handling

```js
try {
  // code that might throw an error
} catch (error) {
  // handle the error
} finally {
  // code that runs regardless of whether an error was caught
}
```
## JSON

```js
// Convert object to JSON string
let data = { key: "value" };
let jsonData = JSON.stringify(data);

// Parse JSON string to object
let parsedData = JSON.parse(jsonData);
```
## Regular Expressions

```js
const pattern = /hello/gi; // Case-insensitive global search

// Test if pattern matches
if (pattern.test(text)) {
  // code
}

// Replace pattern in text
let newText = text.replace(pattern, "hi");
```
## ES6 Features

```js
// Destructuring
const { firstName, lastName } = person;

// Spread operator
const newArray = [...oldArray];

// Template literals
const message = `Hello, ${name}!`;

// Classes
class Animal {
  constructor(name) {
    this.name = name;
  }
}
```

>[!Note]
>Please note that this cheat-sheet is not exhaustive and covers only some of the key concepts in JavaScript. If you need further clarification or additional topics, feel free to ask!

#programming-languages