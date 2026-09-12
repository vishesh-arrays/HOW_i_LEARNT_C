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

#Modifying Elements

In C, you can modify elements of an array after they've been initialized.

Create an integer array with 5 elements:
```
int numbers[5] = {10, 20, 30, 40, 50};
```
To modify an element, use the array name with the index in square brackets:

// Change the third element (index 2) to 35
```
numbers[2] = 35;
```
After executing the above code, the array will contain:

[10, 20, 35, 40, 50]

You can also use variables as indices:
```
int index = 4;
numbers[index] = 55;  // Changes the fifth element (index 4) to 55
```
Now the array contains:
```
[10, 20, 35, 40, 55]
int thirdElement = numbers[2];
```
This stores the value 30 in thirdElement.

Trying to access an element outside the array bounds (like numbers[5] in our example) leads to undefined behavior and can cause program crashes.

# Multidimensional Arrays



A multidimensional array is an array of arrays. In C, you can create a 2D array (the most common multidimensional array), essentially a table with rows and columns.

Declare a 2D array:
```
int matrix[3][4];
```
This creates a 2D array with 3 rows and 4 columns.

You can initialize a 2D array when declaring it:
```
int matrix[3][4] = {
    {1, 2, 3, 4},    // First row
    {5, 6, 7, 8},    // Second row
    {9, 10, 11, 12}  // Third row
};
```
To access elements in a 2D array, use two indices:
```
int value = matrix[1][2];  // Accesses row 1, column 2 (value will be 7)
```
To modify an element in a 2D array:
```
matrix[0][3] = 100;  // Changes the element at row 0, column 3 to 100
```
You can also use nested loops to access all elements in a 2D array:
```
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        printf("%d ", matrix[i][j]);
    }
    printf("\n");  // New line after each row
}
```
