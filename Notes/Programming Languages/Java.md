## History
- Created by James Gosling in 1991 at Sun Microsystems.
- Initially called Oak, in honor of the tree outside Gosling's window.
- Changed to Java because Oak programming language already exists.
- Java was motivated by platform independence in various consumer electronic products like toasters and refrigerators.

- One of the first projects developed using Java was a personal hand-held remote control named Star 7.
- WWW and the Internet were gaining popularity, Gosling realized that Java could be used for Internet programming.

## Features
- Java Virtual Machine (JVM)
	- Provides the hardware platform specs to which you compile all Java tech code.
	- Enables the Java software to be platform-independent.
- Garbage collection
	- Programmer is freed from the burden of having to deallocate memory themselves by having what we call the garbage collection thread.
	- GC thread is responsible for freeing any memory that can be freed.
	- Happens automatically during the lifetime of the Java program.
- Code security
	- Attained in Java through the implementation of its Java Runtime Environment (JRE).
- Robust and flexible

## Phases of Java Program
```mermaid
	
```
1. Writing your programs in a text editor:
`file.java`
2. Compile the program by using the Java Compiler:
`javac TestProgram.java`
3. Run the program by calling the java.exe and passing the main class:
`java TestProgram`

## Errors
- Syntax errors: Mostly created by a syntax or typographical error or missing required tokens. 
- Runtime errors: Happens during the program is running.
- Logic errors: The program doesn't results into an error message, but the program doesn't work in a way that's expected.
## Dissecting the First Java Program
```java
public class Hello
```
- Indicates the name of the class which is **Hello**.
- Public means it can be accessed by other classes.

```java
public static void main(String[] args) {
```
- Starting point of a Java program.

```java
System.out.println("Hello world!");
```
- Prints the new text line `Hello World!` to the screen.

## Coding Guidelines
1. Your Java programs should always end with the `.java` extension.
2. Filenames should match the name of your public class.
3. You should write comments in your code explaining what a certain class does, or what a certain method do. (Personally, comments should explain **why** for your code, not what.)
4. Terminates a statement with a semi-colon.

### Java Identifies
Identifiers
- Tokens that represent names of variables, methods, classes, etc.
- Examples of identifiers are: Hello, main, System, out.
- Java identifiers are case-sensitive.
- Identifiers must begin with either a letter, an underscore "\_" or a dollar sign
- "$"

### Naming
Camel-case
1. For names of classes, capitalize the first letter of the class name. For names of methods and variables, the first letter of the word should start with a small letter.
2. In case of multi-word identifiers, use capital letters to indicate the start of the word.
3. Avoid using underscores at the start of identifier such as \_read or \_write.

## Java Literals
Integer literals
- Default to the data type `int`. An `int` is a _signed_ 32-bit value.

Floating point literals
- Default to the data type `double` which is a 64-bit value. To use a smaller precision (32-bit) float, just append the "f" or "F" character.

Boolean literals
- Only have two values, `true` or `false`.

Character literals
- Single Unicode characters. A Unicode character is a 16-bit character set that replaces the 8-bit ASCII character set.
- Should be enclosed in single quotes.

String literals
- Multiple characters and are enclosed by double quotes.

### Primitive Data Types
Logical - Boolean
- Represents two states: true and false. An example is:
	```java
	boolean result = true;
	```

Textual - char
- Represent a single __Unicode__ character. It must have its literal enclosed in single quotes (' '). For example
	```java
	'a' // The letter a
	'\t' // A tab
	```

String
- It is not a primitive data type (it is a [[Class]]). A String represents a data type that contains multiple characters. It has its literals enclosed in double quotes (“ ”). For example:
	```java
	String messages = "Hello world!";
	```

Integral Data Type has the following ranges:

Integer Length | Name or Type | Range
:--------------|--------------|-------:
8 bits | byte | $-2^7\ \to\ 2^7-1$
16 bits | short | $-2^{15}\ \to\ 2^{15}-1$
32 bits | integer | $-2^{31}\ \to\ 2^{31}-1$
64 bits | long | $-2^{63}\ \to\ 2^{63}-1$

Floating point types has the following ranges:

Float Length | Name or Type | Range
:------------|--------------|-------:
32 bits| float | $-2^{31}\ \to\ 2^{31}-1$
64 bits | double | $-2^{63}\ \to\ 2^{63}-1$