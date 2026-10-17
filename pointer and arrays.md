# Array Names as Pointers
Arrays and pointers in C have a special relationship that's fundamental to understanding how C works with data in memory. When you declare an array, the array name itself acts as a constant pointer to the first element of the array.

This means that when you have an array like int numbers[5];, the name numbers is essentially a pointer that always points to numbers[0]. You can think of the array name as a built-in pointer that you don't need to declare separately.
```
int numbers[5] = {10, 20, 30, 40, 50};
// 'numbers' points to the first element
// numbers == &numbers[0]  // These are equivalent!
```
This equivalence is crucial: numbers and &numbers[0] both give you the exact same memory address. The array name is just a more convenient way to refer to the address of the first element without having to use the address-of operator.

Understanding this relationship opens the door to using pointer techniques with arrays, which can make your code more flexible and efficient. 
The key difference is that unlike regular pointers, array names are constant pointers - you cannot change what they point to.

# Array Elements - Pointers
Now that you understand how array names work as pointers, you can use this knowledge to access array elements in a completely different way. Instead of using the familiar bracket notation like array[i], you can use pointer notation to achieve the same result.

The key insight is that array[i] is exactly equivalent to *(array + i). When you write array + i, you're telling C to move i positions forward from the start of the array. The dereference operator * then gets the value at that location.
```
int numbers[5] = {10, 20, 30, 40, 50};
// These two lines do exactly the same thing:
printf("%d", numbers[2]);    // Prints 30
printf("%d", *(numbers + 2)); // Also prints 30
```
This pointer notation works because C automatically calculates the correct memory address based on the data type size. 
When you add 2 to an integer array pointer, C moves forward by 2 × sizeof(int) bytes, landing exactly on the third element.

Understanding this equivalence gives you flexibility in how you work with arrays and prepares you for more advanced pointer techniques that you'll encounter as you continue learning C.
