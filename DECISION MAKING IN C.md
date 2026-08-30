# If Statement

The `if` statement is a fundamental control flow structure in C that allows your program to make decisions.

An `if` statement executes a block of code only if a specified condition is true.

Basic syntax of an `if` statement:

```c
if (condition) {    // Code to execute if condition is true}
```

Let's look at a simple example:

```c
int age = 20;
if (age >= 18) {    
printf("You are an adult.\n");
}
```

In this example:

- We check if the value in `age` is greater than or equal to 18

- If this condition is true, the message "You are an adult." is printed

- If the condition is false, the program skips the code block and continues with the next statement

# If - Else

The `if-else` statement allows your program to make decisions based on conditions. If a condition is true, one block of code executes; otherwise, a different block executes.

Let's see how to use an `if-else` statement:

First, we define a variable:

```c
int age = 17;
```

Now let's check if the person is an adult:

```c
if (age >= 18) {    
printf("You are an adult.\n");
} else {   
 printf("You are a minor.\n");}
```

Since `age` is 17, which is less than 18, the output will be:

```c
You are a minor.
```

The `if` part checks the condition. When the condition is false, the code in the `else` block executes.

# Else-If

The else-if statement allows you to check multiple conditions in sequence. When the first if condition fails, it moves to check the next else-if condition, and so on.

Start with a basic if statement:

```c
if (grade >= 90) {   
 printf("A grade\n");}
```

Add an else-if to check another condition:

```c
if (grade >= 90) {    
printf("A grade\n");} 
else if (grade >= 80) {    
printf("B grade\n");} 
else if (grade >= 70) {    
printf("C grade\n");}
```

Finally, you can add an else statement at the end to handle all other cases:

```c
if (grade >= 90) {    
printf("A grade\n");} 
else if (grade >= 80) {
    printf("B grade\n");}
     else if (grade >= 70) {
         printf("C grade\n");}
          else {    printf("Failed\n");}
```

# Switch Case

The `switch` statement is a multi-way decision maker that tests whether an expression matches one of several constant integer values, and branches accordingly.

First, define an integer to use with switch:

```c
int day = 3;
```

Then create a switch statement that evaluates the variable:

```c
switch (day) {    
case 1:        
printf("Monday\n");        
break;    
case 2:        
printf("Tuesday\n");        
break;    
case 3:        
printf("Wednesday\n");        
break;    
default:        
printf("Other day\n");}
```

In this example:

- Each `case` represents a possible value of `day`
- When `day` equals `3`, "Wednesday" will be printed

- The `break` statement exits the switch
- The `default` case handles all values not explicitly covered

Without `break`, execution would "fall through" to the next case.

# Ternary Conditional Operator

The ternary conditional operator is a shorthand way to express an if-else statement in a single line.

The syntax is:

```c
condition ? value_if_true : value_if_false;
```

Let's look at an example. First, here's a traditional if-else statement:

```c
int max;if (a > b) {    
max = a;} 
else {    
max = b;}
```

Now, let's rewrite it using the ternary operator:

```c
int max = (a > b) ? a : b;
```

In this example:

- `a > b` is the condition
- If the condition is true, `a` is returned
- If the condition is false, `b` is returned

The ternary operator can also be nested, but this can make code harder to read:

```c
int x = (a > b) ? ((a > c) ? a : c) : ((b > c) ? b : c);
```