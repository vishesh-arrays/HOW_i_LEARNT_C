# Declare a Function



A function in C is a block of code that performs a specific task. Functions help organize code, make it reusable, and improve readability. Here's the basic structure of a function declaration in C:
```
return_type function_name(parameter1_type parameter1_name, parameter2_type parameter2_name, ...) {
    // code to be executed
    return value; // if the return_type is not void
}
```
For example, a simple function that greets the user might look like this:
```
void greet() {
    printf("Hello, welcome to C programming!");
}
```
To use (call) this function in your main program, you would write:
```
int main() {
    greet();
    return 0;
}
```
Functions can also take parameters and return values, which we'll explore in later lessons.

# Return Types



When defining a function in C, you need to specify what type of value it will return to the caller. This is known as the return type.

Declare a function that returns an integer:
```
int sum(int a, int b) {
    return a + b;
}
```
The int before the function name specifies that this function will return an integer value.

Call the function and store its return value:
```
int result = sum(5, 3);
```
After executing this code, result will contain the value 8.

You can also use other data types as return types:
```
float average(float a, float b) {
    return (a + b) / 2;
}
```
This function returns a float value.


# Parameters



Functions in C can accept parameters (also called arguments), which are values passed to the function when it is called.

Declare a function that takes parameters:
```
int add(int a, int b) {
    return a + b;
}
```
In this example, add is a function that takes two integer parameters, a and b, and returns their sum.

Call a function with parameters:
```
int result = add(5, 3);
```
After executing the above code, result contains:
```
8
```
You can also use variables as arguments:
```
int x = 10;
int y = 20;
int sum = add(x, y);
```
After executing the above code, sum contains:
```
30
```
# Recursion Basics



Recursion is a technique where a function calls itself to solve a problem. It's like solving a big problem by breaking it into smaller, similar problems.

Let's look at a simple recursive function that calculates factorial:
```
int factorial(int n) {
    // Base case: factorial of 0 or 1 is 1
    if (n <= 1) {
        return 1;
    }
    
    // Recursive case: n! = n * (n-1)!
    return n * factorial(n - 1);
}
```
Every recursive function needs:

A base case to stop recursion
A recursive case that moves toward the base case
```
For example, calculating factorial(3):

factorial(3) calls factorial(2)
factorial(2) calls factorial(1)
factorial(1) returns 1 (base case)
factorial(2) returns 2 * 1 = 2
factorial(3) returns 3 * 2 = 6
```
# Function Prototypes



In C, we can declare a function before we use it. A function prototype tells the compiler about a function's name, parameters, and return type before the actual function is defined.

Create a function prototype for a function that adds two integers:
```
int add(int a, int b);
Then define the function:

int add(int a, int b) {
    return a + b;
}
```
The prototype is usually above the main, while the function itself is below the main, so the code looks cleaner.

Now you can use this function in the main:
```
int main() {
    int result = add(5, 3);
    printf("%d", result);
    return 0;
}
```
Without the prototype, if you call the function before its definition, you'll get a compiler error.

#CALCULATOR
```
#include <stdio.h>

int add(int a, int b) { return a + b; }
int subtract(int a, int b) { return a - b; }
int multiply(int a, int b) { return a * b; }
int divide(int a, int b);
int calculate(int a, int b, char operation);

int main() {
    int a, b;
    char op;

    if (scanf("%d %d %c", &a, &b, &op) != 3) {
        scanf(" %c", &op);
        if (op == 'q') {
            return 0;
        }
        printf("Invalid input\n");
        return 1;
    }

    int result = calculate(a, b, op);
    if (result != -99999) {
        printf("%d\n", result);
    }
    else {
        printf("Invalid input\n");
    }

    return 0;
}

int divide(int a, int b) {
    if (b == 0) {
        return -99999;
    }
    return a / b;
}

int calculate(int a, int b, char operation) {
    switch (operation) {
        case '+':
            return add(a, b);
        case '-':
            return subtract(a, b);
        case '*':
            return multiply(a, b);
        case '/':
            return divide(a, b);
        default:
            return -99999;
    }
}
```
