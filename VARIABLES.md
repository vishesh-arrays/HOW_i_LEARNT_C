# Data Types

In C, every piece of data in your program has a specific type. Data types define what kind of data a variable can hold and how much memory it needs. Let's look at the basic data types in C:

Create an integer variable:

```c
int age;
```

This declares a variable named `age` that can hold whole numbers.

```c
age = 25;
```

This assigns the value 25 to `age`. But you can also declare and initialize in one step:

```c
int score = 100;
```

Here, `int score = 100;` declares the variable and sets its value at the same time.

Here are the primary data types in C:

```c
int number = 42;        // Integer (whole number)float price = 10.5f;    // Floating-point (decimal)double pi = 3.14159;    // Double precision floating-pointchar grade = 'A';       // Single character
```

**int** stores whole numbers. **float** stores decimal numbers — the `f` suffix (e.g. `10.5f`) tells C to treat the value as a `float` rather than a `double`. **double** stores decimal numbers with greater precision than `float`. **char** stores a single character enclosed in single quotes.


# Integer

In C, integers are whole numbers without any decimal points. They are one of the most common data types you'll work with.

Declaring, initializing, and modifying integers:

```c
int age; // Declaringint score = 100; // Declaring and initializingscore = 90; // Modifying
```

Print an integer using printf:

```c
printf("%d", score);
```

The `int` type stores whole numbers.

# Float - Double

Float and double are data types used to store decimal numbers in C.

Declare a float variable:

```c
float price = 19.99f;
```

Notice the 'f' suffix, which tells C this is a float value.

Declare a double variable:

```c
double pi = 3.14159265359;
```

The main differences between float and double:

1. Precision: Double has higher precision than float
    - Float: ~7 decimal digits
    - Double: ~15 decimal digits

2. Size:
    - Float: 4 bytes
    - Double: 8 bytes

3. Range:
    - Float: 1.2E-38 to 3.4E+38
    - Double: 2.3E-308 to 1.7E+308

Print a float value:

```c
float temperature = 98.6f;printf("Temperature is %f degrees\n", temperature);
```

Print with specific decimal places:

```c
printf("Temperature is %.1f degrees\n", temperature);
```

This will show: “Temperature is 98.6 degrees”

**To print both variables in a single `printf`, use `%.1f` as a placeholder for each number.

# Characters

In C, the `char` data type is used to store a single character. Characters in C are enclosed in single quotes.

Declare a character variable:

```c
char letter;
```

Assign a character to the variable:

```c
letter = 'A';
```

You can also declare and initialize in one line:

```c
char grade = 'B';
```

A character occupies 1 byte of memory and is actually stored as an integer representing its ASCII value. For example, 'A' is stored as 65, 'B' as 66, and so on.

**You can print a character using the `%c` format specifier:

```c
printf("The letter is: %c\n", letter);
```

# Booleans

In C, there is no built-in boolean data type like in other languages. Instead, C uses integers to represent boolean values.

Define an integer to represent a boolean value:

```c
int isTrue = 1;  // Represents trueint isFalse = 0; // Represents false
```

In C, any non-zero value is considered "true" while zero is considered "false". 

Use these boolean values in conditions:

```c
int age = 25;int isAdult = (age > 17);printf("Is adult? %d\n", isAdult);
```

```c
Output:Is adult? 1
```

You can use comparison operators to produce boolean results. For example, `>` checks if the left value is greater than the right, and `>=` checks if the left value is greater than _or equal to_ the right:

```c
int age = 18;int isAdult = (age >= 18); // true if age is 18 or olderprintf("Is adult? %d\n", isAdult);
```

```c
Output:Is adult? 1
```

Starting with C99, you can include the `<stdbool.h>` header to use the boolean type:

```c
#include <stdbool.h>bool isTrue = true;   // Now using actual boolean typebool isFalse = false; // Using predefined constants
```

But you will learn more about the usage of booleans later throughout your journey



# Constants

Constants in C are variables whose values cannot be changed during program execution. They are useful for values that should remain fixed throughout your program.
There are 2 Types of Constants:
1. primary like = integers, real and character constants
2. secondary like = pointers, arrays.



Define a constant using the `#define` directive:  

```c
#define PI 3.14159
```

The above line creates a constant named PI with the value 3.14159.

Another way to create constants is by using the `const` keyword:  

```c
const float TAX_RATE = 0.07;
```

This creates a constant named TAX_RATE with the value 0.07. Note that attempting to modify a constant variable after it has been defined will result in a compilation error.

Use constants in your program like regular variables:  

```c
float area = PI * radius * radius;float tax = price * TAX_RATE;
```

Constants make your code more readable and easier to maintain. If you need to change a value used in multiple places, you only need to update it once.


# printf Basics

In C, the `printf()` function is used to print formatted output to the console. It's part of the standard input/output library `<stdio.h>`.

The basic syntax of `printf()` is:

```c
printf("format string", argument1, argument2, ...);
```

The format string can contain:

- Plain text, which is printed as-is
- Format specifiers, which start with % and are replaced by the values of the arguments

__Here are some common format specifiers:

- `%d` for integers
- `%f` for floating-point numbers

- `%c` for characters
- `%s` for strings

Example:

```c
int age = 25;
printf("I am %d years old.\n", age);
```

This will output: `I am 25 years old.`

The `\n` at the end of the string is a newline character, which moves the cursor to the next line after printing.


# Type Casting Part 1

Type casting in C allows you to convert a value from one data type to another. This is useful when you need to perform operations between different data types.

There are two main types of type casting:

1. Implicit casting (automatic)
2. Explicit casting (manual)

Let's start with implicit casting:

Implicit casting happens automatically when converting from a smaller data type to a larger one:

```c
int num = 10;double decimal_num;// Implicit casting from int to doubledecimal_num = num;
```

After executing the above code, `decimal_num` will have the value `10.0`

This works because a double can store all possible values of an int without losing any data. The conversion is safe, so C does it automatically.

Common implicit casting paths:

- char → int → long → float → double

Now let's look at explicit casting:

Explicit casting is done manually by placing the target data type in parentheses before the value you want to convert. This is necessary when converting from a larger data type to a smaller one, where data loss may occur:

```c
double decimal_num = 5.65;int num;// Explicit casting from double to intnum = (int)decimal_num;
```

After executing the above code, `num` will have the value `5`

Notice that the decimal part is truncated (not rounded) when casting from double to int. The syntax for explicit casting is:

```c
(target_type) value
```

Because this conversion can lose data, C requires you to do it explicitly — this tells the compiler you are aware of the potential data loss.

# Type Casting Part 2

In Part 1, we looked at implicit type casting. Now, let's explore explicit type casting in C.

Explicit type casting (manual conversion) is when you forcefully convert one data type to another using the cast operator.

The syntax for explicit casting is:

```python
(target_type) expression
```

Let's convert a float to an integer:

```c
float price = 45.95;int rounded_price = (int) price;
```

After executing the above code, `rounded_price` will be:

45

Notice that the decimal part is truncated (not rounded).

We can also cast characters to integers to get their ASCII values:

```c
char letter = 'A';int ascii_value = (int) letter;
```

After executing the above code, `ascii_value` will be:

65

**Remember, type casting can lead to data loss, especially when converting from a larger data type to a smaller one.

