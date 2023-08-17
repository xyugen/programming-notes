# Variables and Data Types

```c
// Variable declaration
int age = 30;
float salary = 50000.50;
char grade = 'A';
```

## Control Structures

```c
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

```c
// Function declaration
int add(int a, int b) {
  return a + b;
}
```

## Arrays

```c
int numbers[] = { 1, 2, 3, 4, 5 };

// Access element
int firstNumber = numbers[0];

// Loop through array
for (int i = 0; i < 5; i++) {
  // code
}
```

## Pointers

```c
int value = 42;
int *ptr = &value;

// Access value through pointer
int retrievedValue = *ptr;
```

## Structures

```c
struct Person {
  char name[50];
  int age;
};

// Creating a structure variable
struct Person person;
strcpy(person.name, "John");
person.age = 30;
```

## Memory Allocation

```c
// Dynamic memory allocation
int *dynamicArray = (int *)malloc(5 * sizeof(int));
free(dynamicArray);
```

## File I/O

```c
// Reading from a file
FILE *file = fopen("input.txt", "r");
char line[100];
while (fgets(line, sizeof(line), file)) {
  // process the line
}
fclose(file);

// Writing to a file
file = fopen("output.txt", "w");
fprintf(file, "Hello, world!");
fclose(file);
```

## Preprocessor Directives

```c
#include <stdio.h>
#define MAX_SIZE 100
#ifdef DEBUG
  // code for debugging
#endif
```

## Function Pointers

```c
int add(int a, int b) {
  return a + b;
}

int (*functionPtr)(int, int) = add;
int result = functionPtr(5, 10);
```

## Enumerations

```c
enum Days { MON, TUE, WED, THU, FRI, SAT, SUN };
enum Days today = WED;
```

## Command Line Arguments

```c
int main(int argc, char *argv[]) {
  // code
  return 0;
}
```

## Memory Management

```c
void *ptr = malloc(10);
// ...
free(ptr);
```

## Multithreading (Using Pthreads Library)

```c
#include <pthread.h>

void *myThreadFunction(void *arg) {
  // code to run in the thread
  pthread_exit(NULL);
}

int main() {
  pthread_t thread;
  pthread_create(&thread, NULL, myThreadFunction, NULL);
  pthread_join(thread, NULL);
  return 0;
}
```

# Advanced

## Function Pointers

```c
#include <stdio.h>

int add(int a, int b) {
  return a + b;
}

int subtract(int a, int b) {
  return a - b;
}

int main() {
  int (*operation)(int, int);
  operation = add;

  int result = operation(5, 3); // result = 8

  operation = subtract;
  result = operation(10, 3); // result = 7

  return 0;
}
```

## Dynamic Memory Allocation

```c
#include <stdlib.h>

int main() {
  int *dynamicArray = (int *)malloc(5 * sizeof(int));
  // ...
  free(dynamicArray);
  return 0;
}
```

## Linked Lists

```c
struct Node {
  int data;
  struct Node *next;
};

struct Node *head = NULL;

// Insert at the beginning
void insert(int data) {
  struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
  newNode->data = data;
  newNode->next = head;
  head = newNode;
}

// Traversing the list
void traverse() {
  struct Node *current = head;
  while (current != NULL) {
    // process current->data
    current = current->next;
  }
}
```

## Pointers to Functions

```c
#include <stdio.h>

int main() {
  FILE *file = fopen("file.txt", "r");
  if (file == NULL) {
    perror("Error opening file");
    return 1;
  }

  char line[100];
  while (fgets(line, sizeof(line), file)) {
    // process line
  }

  fclose(file);
  return 0;
}
```

## File I/O

```c
#include <stdio.h>

int main() {
  FILE *file = fopen("file.txt", "r");
  if (file == NULL) {
    perror("Error opening file");
    return 1;
  }

  char line[100];
  while (fgets(line, sizeof(line), file)) {
    // process line
  }

  fclose(file);
  return 0;
}
```

## Command Line Arguments

```c
#include <stdio.h>

int main(int argc, char *argv[]) {
  for (int i = 0; i < argc; i++) {
    printf("Argument %d: %s\n", i, argv[i]);
  }
  return 0;
}
```

## Multithreading (Using Pthreads Library)

```c
#include <stdio.h>
#include <pthread.h>

void *myThreadFunction(void *arg) {
  // code to run in the thread
  return NULL;
}

int main() {
  pthread_t thread;
  pthread_create(&thread, NULL, myThreadFunction, NULL);
  pthread_join(thread, NULL);
  return 0;
}
```

## Structures and Unions

```c
#include <stdio.h>

int main() {
  int num = 5; // Binary: 0101

  int result = num << 2; // Left shift: 10100 (20 in decimal)
  printf("Result: %d\n", result);

  return 0;
}
```

## Bitwise Manipulation

```c
#include <stdio.h>

int main() {
  int num = 5; // Binary: 0101

  int result = num << 2; // Left shift: 10100 (20 in decimal)
  printf("Result: %d\n", result);

  return 0;
}
```

>[!Note]
>This advanced C programming cheat-sheet covers more intricate concepts and techniques.