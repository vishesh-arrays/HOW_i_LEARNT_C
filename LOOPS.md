
The for loop is a control structure that allows you to execute a block of code repeatedly for a specific number of times.

A for loop has three components:

- Initialization (executed once before the loop starts)
- Condition (checked before each iteration)

- Update (executed after each iteration)

```c
for (initialization; condition; update)
 {    // code to be executed}
```

Let's create a simple for loop that counts from 1 to 5:

```c
for (int i = 1; i <= 5; i++) {
    printf("%d ", i);}
```

After executing the above code, the output will be:

```python
1 2 3 4 5
```

How this works:

1. First, we initialize `i` to 1
2. Then we check if `i <= 5` (true, so we execute the loop body)

3. We print the value of `i`
4. We increment `i` by 1
5. We repeat steps 2-4 until the condition becomes false

# While Loop

The `while` loop lets you repeatedly execute a block of code as long as a specified condition is true.

Here's the basic syntax:

```c
while (condition) {
    // code to be repeated}
```

Let's create a simple counter:  
Initialize a counter variable

```c
int count = 1;
```

Create a while loop that runs as long as count is less than or equal to 5

```c
while (count <= 5) {    
printf("%d ", count);    
count++;}
```

After executing the code, the output will be:

```python
1 2 3 4 5
```

The loop continues until `count` becomes 6, at which point the condition `count <= 5` becomes false, and the loop ends.

# Do While Loop

The do-while loop is similar to the while loop, but with one important difference: the code block is executed at least once, and then the condition is checked.

Create a do-while loop:

```c
do {    // Code to be executed} while (condition);
```

Let's create a program that asks the user to enter a positive number:

```c
int number;do {   
 printf("Please enter a positive number: ");    
 scanf("%d", &number);} 
 while (number <= 0);
 printf("You entered: %d\n", number);
```

In this example:

1. The code inside the do block runs first, asking for input
2. After getting the input, the condition `number <= 0` is checked

3. If the condition is true (the number is not positive), the loop repeats
4. If the condition is false (the number is positive), the loop stops

The do-while loop is perfect for situations where you need to execute the code at least once, regardless of the condition.


# Break

The `break` statement stops the loop instantly when it's encountered.

For example,

```c
for (int i = 0; i < 10; i++) {
    if (i == 6) {        
    break;    
    }    printf("%d ", i);}
```

In the following example, the loop iterates regularly until it reaches the number 6. Then the program enters the `if` statement and executes the `break` statement. This **exits** the loop immediately.

The output is:

```c
0 1 2 3 4 5
```

# Continue

The `continue` statement stops the current iteration and continues to the next iteration. For example:

```c
for (int i = 3; i < 9; i++) {    
if (i == 5) {        
continue;    
}    printf("%d ", i);}
```

The loop will iterate through all of the numbers. When it reaches ⁣`i=5` it will skip that iteration and continue to the next one. The output is:

```c
3 4 6 7 8
```

Notice, number 5 is not in the output.