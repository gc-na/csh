<!--
Meta Description: # Understanding Unsigned in C: A Comprehensive Guide ## Synopsis In C programming, the `unsigned` keyword modifies integer types to represent only non...
Meta Keywords: unsigned, int, integer, values, types
-->

# Understanding Unsigned in C: A Comprehensive Guide

## Synopsis
In C programming, the `unsigned` keyword modifies integer types to represent only non-negative values, effectively doubling the maximum positive range of standard integer types. 

## Documentation
The `unsigned` modifier is used in C to specify that a variable can only hold non-negative values. This is particularly useful when working with data that cannot logically be negative, such as sizes, counts, and indices.

### Purpose
The main purpose of using `unsigned` types is to provide a larger positive range by eliminating negative values. For example, an `unsigned int` can store values from 0 to 4,294,967,295, while a standard `int` can typically store values from -2,147,483,648 to 2,147,483,647. 

### Usage
The `unsigned` modifier can be applied to various integer data types in C, including:
- `unsigned int`
- `unsigned short`
- `unsigned long`
- `unsigned long long`

### Declaration
To declare an unsigned variable, simply prefix the type with the `unsigned` keyword:
```c
unsigned int myVar;
unsigned long myLongVar;
```

## Examples
### Example 1: Basic Declaration
```c
#include <stdio.h>

int main() {
    unsigned int num = 10;
    printf("The unsigned number is: %u\n", num);
    return 0;
}
```
Output:
```
The unsigned number is: 10
```

### Example 2: Overflow Behavior
```c
#include <stdio.h>

int main() {
    unsigned int num = 0;
    num = num - 1; // Underflow occurs
    printf("After underflow, the number is: %u\n", num);
    return 0;
}
```
Output:
```
After underflow, the number is: 4294967295
```

## Explanation
### Common Pitfalls
1. **Underflow**: Subtracting from zero in an unsigned variable leads to underflow, wrapping the value around to the maximum representable value.
  
2. **Implicit Type Conversions**: Be cautious with arithmetic operations involving mixed signed and unsigned integers, as this can lead to unexpected results. For instance, if you perform a subtraction between a signed and unsigned integer, the signed integer may be implicitly converted to unsigned, potentially leading to large positive numbers.

3. **Integer Promotion**: When performing operations between different integer types, C promotes them to a common type, which can sometimes lead to surprises if not accounted for.

4. **Printing Unsigned Values**: Use the correct format specifiers when printing unsigned values (`%u` for `unsigned int`, `%lu` for `unsigned long`, etc.) to avoid undefined behavior.

## One Line Summary
The `unsigned` keyword in C allows integer types to store only non-negative values, effectively expanding their maximum positive range.