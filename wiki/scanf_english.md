<!--
Meta Description: # Understanding scanf in C: A Comprehensive Guide ## Synopsis `scanf` is a standard input function in the C programming language that enables users to...
Meta Keywords: scanf, input, format, number, int
-->

# Understanding scanf in C: A Comprehensive Guide

## Synopsis
`scanf` is a standard input function in the C programming language that enables users to read formatted data from the standard input (stdin), such as the keyboard.

## Documentation

### Purpose
The `scanf` function is primarily used for taking input from the user in a formatted way. It can read various data types, including integers, floating-point numbers, and strings, according to the specified format.

### Usage
The prototype of the `scanf` function is as follows:

```c
int scanf(const char *format, ...);
```

- `format`: A string that specifies the format of the input to be read. It contains conversion specifiers that dictate how the input should be interpreted.
- `...`: A variable number of arguments, which are pointers to variables where the input data will be stored.

#### Format Specifiers
Common format specifiers include:
- `%d`: Reads an integer.
- `%f`: Reads a floating-point number.
- `%s`: Reads a string (until whitespace).
- `%c`: Reads a single character.

### Return Value
The function returns the number of input items successfully matched and assigned, which can be less than specified if an input failure occurs.

## Examples

### Basic Usage
```c
#include <stdio.h>

int main() {
    int number;
    printf("Enter an integer: ");
    scanf("%d", &number);
    printf("You entered: %d\n", number);
    return 0;
}
```

### Reading Multiple Values
```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two integers: ");
    scanf("%d %d", &a, &b);
    printf("You entered: %d and %d\n", a, b);
    return 0;
}
```

### Reading a String
```c
#include <stdio.h>

int main() {
    char name[50];
    printf("Enter your name: ");
    scanf("%s", name);
    printf("Hello, %s!\n", name);
    return 0;
}
```

## Explanation

### Common Pitfalls
1. **Buffer Overflow**: When reading strings, `scanf` does not perform bounds checking. This can lead to buffer overflows. It's safer to specify a maximum width, for example, `%49s` for a 50-character array.
   
   ```c
   scanf("%49s", name);
   ```

2. **Input Mismatch**: If the input does not match the expected format, `scanf` may not behave as intended. For instance, entering a letter when expecting an integer will cause it to fail.

3. **Ignoring Whitespace**: When using `%s`, `scanf` stops reading at the first whitespace. If you need to read a full line including spaces, consider using `fgets()` instead.

4. **Use of Address-of Operator**: The address-of operator (`&`) is necessary for all types except for strings, as arrays decay to pointers. Forgetting `&` can lead to undefined behavior.

5. **Return Value Checking**: Always check the return value of `scanf` to ensure that the expected number of inputs was received.

## One Line Summary
`scanf` is a versatile C function for reading formatted input from standard input, but it requires careful handling to avoid common pitfalls.