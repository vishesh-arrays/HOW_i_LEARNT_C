# Declaring Arrays



Arrays in C allow you to store multiple values of the same data type under a single variable name.

Declare an integer array with 5 elements:
```
int numbers[5];
```
This creates an array named numbers that can hold 5 integers.

You can also initialize an array with values when declaring it:
```
int numbers[5] = {10, 20, 30, 40, 50};
```
If you initialize all elements, you can let C determine the size:
```
int numbers[] = {10, 20, 30, 40, 50};
```
C will automatically create an array with 5 elements.

Arrays in C are zero-indexed, which means the first element is at index 0.

# Accessing Elements



Arrays store multiple values of the same type. We use the index position to access individual elements in an array.

In C, array indices start at 0. This means the first element is at index 0, the second at index 1, and so on.

Create an integer array with 5 elements:
```
int numbers[5] = {10, 20, 30, 40, 50};
```
Access the first element (index 0):
```
int firstElement = numbers[0];
```
After executing the above code, firstElement contains:

10
Access the third element (index 2):
```
int thirdElement = numbers[2];
```
This stores the value 30 in thirdElement.

Trying to access an element outside the array bounds (like numbers[5] in our example) leads to undefined behavior and can cause program crashes.

# Accessing Elements



Arrays store multiple values of the same type. We use the index position to access individual elements in an array.

In C, array indices start at 0. This means the first element is at index 0, the second at index 1, and so on.

Create an integer array with 5 elements:
```
int numbers[5] = {10, 20, 30, 40, 50};
```
Access the first element (index 0):
```
int firstElement = numbers[0];
```
After executing the above code, firstElement contains:

10
Access the third element (index 2):
```
int thirdElement = numbers[2];
```
This stores the value 30 in thirdElement.

Trying to access an element outside the array bounds (like numbers[5] in our example) leads to undefined behavior and can cause program crashes.
