# Arithmetic Operators

Arithmetic operators in C are used to perform basic mathematical operations. The most common arithmetic operators are:

- `+` (addition)
- `-` (subtraction)
- `*` (multiplication)
- `/` (division)

Here's how you can use these operators:

```c
int a = 10;
int b = 5;
int sum = a + b; 
      // sum is 15int difference = a - b;
       // difference is 5int product = a * b; 
        // product is 50int quotient = a / b; 
         // quotient is 2
```

Note that when dividing two integers, the result will be an integer (fractional part is truncated). For example:

```c
int result = 7 / 2;  // result is 3, not 3.5
```

To get a floating-point result, at least one of the operands should be a float:

```c
float result = 7.0 / 2;  // result is 3.5
```

# Modulo Operator

The modulo operator `%` in C gives the remainder of a division. It's used with a simple syntax:

```c
result = dividend % divisor;
```

- **dividend:** The number being divided.
- **divisor:** The number that divides the dividend.
- **result:** The remainder of the division.

For example:

```c
int result = 10 % 3;
```

Here, 10 is divided by 3. 3 goes into 10 three times, with a remainder of 1. So, `result` will be 1.

The modulo operator is often used for checking if a number is even or odd:

- If a number is even, dividing it by 2 will leave a remainder of 0.
- If a number is odd, dividing it by 2 will leave a remainder of 1.


# Increment/Decrement

In C, increment (++) and decrement (--) operators allow you to increase or decrease the value of a variable by 1.

Let's use an integer variable:

```c
int counter = 5;
```

To increment by 1, use the ++ operator:

```c
counter++;  // Increases counter to 6
```

To decrement by 1, use the -- operator:

```c
counter--;  // Decreases counter to 5
```

These operators can be used in two ways:

**1. Prefix form (++counter or --counter):

```c
int a = 5;
int b = ++a;  // a is incremented to 6, then b is assigned 6
```

**1. Postfix form (counter++ or counter--):

```c
int x = 5;
int y = x++;  // y is assigned 5, then x is incremented to 6
```

The difference is when the increment happens relative to the assignment.

# Assignment Operators

Assignment operators in C are used to assign values to variables. The most basic assignment operator is the equals sign `=`. However, C also provides compound assignment operators that combine arithmetic operations with assignment.

Here are the common assignment operators:

- `=` : Simple assignment

- `+=` : Add and assign
- `-=` : Subtract and assign

- `*=` : Multiply and assign
- `/=` : Divide and assign
- `%=` : Modulo and assign

For example, instead of writing:

```c
int a = 5;a = a + 3; // a now holds 8
```

We can simplify it by writing:

```c
int a = 5;a += 3; // a now holds 8
```

The `+=` is adding 3 to `a` and then assigning the result back to `a`.

# Relational Operators

**Comparison operators** are used to compare two operands.

Sometimes we need to check whether an operand is bigger/smaller/... than another operand.

The following table shows possible operators for comparison:

|Operator|Meaning|Example|
|---|---|---|
|==|Equal|1 == 2 returns 0 (false)|
|!=|Not Equal|1 != 2 returns 1 (true)|
|>|Greater Than|1 > 2 returns 0 (false)|
|<|Less Than|1 < 2 returns 1 (true)|
|>=|Greater or Equal|1 >= 2 returns 0 (false)|
|<=|Less or Equal|1 <= 2 returns 1 (true)|

  
The comparison operator returns `1` if the comparison is true or `0` if it's false.

For example:

```c
int var1 = 13;
int var2 = 12;
int var3 = var1 != var2;
```

`var3` will hold `1` because `var1` and `var2` are not equal

# Logical Operators Part 1

**Logical operators** are used to check combinations of comparisons that return `1` (true) or `0` (false).

For example, the following statement contains two comparisons: 

Is 5 greater than 3 **and** less than 6?

|Operator|Meaning|Example|
|---|---|---|
|`&&`|And - `1` if **all** operands are `1`|`a && b`|
|`\|`|Or - `1` if **any** operand is `1`|`a \| b`|
|`!`|Not - `1` if the operand is `0`|`!a`|

Let's see some examples:

5 is greater than 3 and 1 equals 1:

```c
int b1 = (5 > 3) && (1 == 1); // holds 1 (true)
```

**Explanation**: All of the operands are `1`, so `b1` will hold `1` (`and` operation is `1` if both operands are `1`) .

5 is not equal to 4 or 5 equals 2:

```c
int b2 = !(5 == 4) || (5 == 2); // holds 1 (true)
```

**Explanation**: The first operand (`5 != 4`) is `1` so `b2` is also `1` (`or` operation is `1` if either one of the operands is `1`)

# Logical Operators Part 2

Logical operators have a special table called a "Truth table" that shows what the combination of logical operators returns.

Truth table for the `and` (`&&`) operator:

|a|b|a && b|
|---|---|---|
|0|0|0|
|0|1|0|
|1|0|0|
|1|1|1|

The only way to get a `1` (true) for the `and` (`&&`) operator is if both `a` and `b` are `1` (true)

Truth table for the `or` (`||`) operator:

|a|b|a \| b|
|---|---|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|1|

In this case, to get a `1` (true) result, either `a` or `b` should be `1` (true).

Truth table for the `not` (`!`) operator:

|a|!a|
|---|---|
|0|1|
|1|0|

Here, the value of `a` is reversed. If `a` is `0` (false) then `!a` is `1` (true)

# Logical Operators Part 3

When checking multiple conditions, the program stops checking as soon as it knows the final answer. This is called short-circuit evaluation.

For example:

```c
int x = 0;int y = 5;int result = (x != 0) && (y / x > 2);
```

Here `x` equals `0`, therefore, it will not evaluate `y / x > 2`. If we were to reverse the order:

```c
int result = (y / x > 2) && (x != 0);
```

This will result in an error because `y` will be divided by 0, which is undefined in C. So it is a good practice to think operations through, so you can get the correct and effective, but errorless code.

This technique is used to optimize the evaluation of logical expressions. For example:

```c
int a = 0;
int b = 2;
int c = 3;
int d = 5;
int result = (a > 0 && b < 2) || (c < -5 && d < 10);
```

In this example, `b < 2` and `d < 10` will not be evaluated because `a > 0` and `c < -5` are both false.