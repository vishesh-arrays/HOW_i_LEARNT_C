Hello World!

The **"Hello World!"** program is simple and outputs `Hello, World!` to the screen. It's often used as a first program when learning a new programming language.

In C, we use the `printf()` function to print output to the console. The text to be printed is placed within double quotes and followed by a semicolon.

```c
#include <stdio.h>int main() {    printf("Hello, World!");}
```

The `#include <stdio.h>` line includes the standard input/output library, which contains the `printf()` function

# Comments

**Comments** are notes you write inside your code. The compiler completely ignores them - they exist only to help humans understand the code.

To write a single-line comment, use `//`. Everything after `//` until the end of the line is ignored:

```c
// This is a commentprintf("Hello, World!");
```

A comment can also be written at the end of a line, after the code:

```c
printf("Hello, World!"); // This prints Hello, World!
```

For comments that span several lines, use `/*` to start and `*/` to end:

```c
/* This is a multi-line comment.   The compiler ignores all of it. */printf("Welcome!");
```

Comments can also temporarily **disable** a line of code without deleting it:

```c
// printf("This line will NOT run");printf("This line will run");
```

**Note:** Every multi-line comment that starts with `/*` must be closed with `*/`, otherwise the compiler treats everything after it as a comment.

# Basic Program Structure

Every C program must start with header directives like:

```c
 #include <stdio.h> // Header for input/output #include <math.h> // Header for math functions
```

These directives include header files containing declarations for functions and objects your program uses.

All executable code must be inside the main() function, which is the entry point of the program. For example:

```c
#include <stdio.h> // Header for input/outputint main() { // Main function    printf("This is my first C program!"); // Output statement    return 0; // Return statement - not mandatory in modern C }
```

Remember, every statement ends with a semicolon (;), except for code blocks in curly braces.. The semicolon is mandatory and tells C that you've reached the end of a statement.

