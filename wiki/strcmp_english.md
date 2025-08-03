<!--
Meta Description: # Understanding `strcmp` in C: A Comprehensive Guide ## Synopsis `strcmp` is a standard library function in C used to compare two strings. It returns ...
Meta Keywords: strcmp, string, strings, str1, str2
-->

# Understanding `strcmp` in C: A Comprehensive Guide

## Synopsis
`strcmp` is a standard library function in C used to compare two strings. It returns an integer that indicates the relationship between the two strings, making it a fundamental tool for string manipulation and comparison in C programming.

## Documentation

### Purpose
The `strcmp` function is designed to compare two null-terminated strings lexicographically. It determines if one string is less than, greater than, or equal to another string based on the ASCII values of the characters involved.

### Usage
To use the `strcmp` function, you must include the `<string.h>` header file in your program. The function's prototype is as follows:

```c
int strcmp(const char *str1, const char *str2);
```

### Parameters
- `str1`: A pointer to the first null-terminated string.
- `str2`: A pointer to the second null-terminated string.

### Return Value
`strcmp` returns an integer value:
- **Zero (0)**: If both strings are equal.
- **Negative value**: If `str1` is lexicographically less than `str2`.
- **Positive value**: If `str1` is lexicographically greater than `str2`.

### Example
Here’s a simple example demonstrating how to use `strcmp`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hello";
    const char *str2 = "World";
    const char *str3 = "Hello";

    int result1 = strcmp(str1, str2);
    int result2 = strcmp(str1, str3);

    printf("Result of comparing '%s' and '%s': %d\n", str1, str2, result1); // Outputs a negative value
    printf("Result of comparing '%s' and '%s': %d\n", str1, str3, result2); // Outputs 0

    return 0;
}
```

## Explanation
### Common Pitfalls
- **Case Sensitivity**: `strcmp` is case-sensitive. For example, "hello" and "Hello" will not be considered equal. To perform case-insensitive comparisons, use `strcasecmp` or `stricmp` (where available).
  
- **Null Pointers**: Passing a NULL pointer to `strcmp` can lead to undefined behavior. Always ensure that both strings are valid before calling the function.

- **Unterminated Strings**: If either string is not properly null-terminated, `strcmp` may read beyond the string memory, leading to undefined behavior. Always ensure your strings are properly terminated.

- **Memory Safety**: Avoid comparing strings that are modified concurrently in multi-threaded applications, as this can lead to race conditions.

### Additional Notes
`strcmp` performs comparisons based on the ASCII values of characters. This means that uppercase letters are considered less than lowercase letters, which can affect the results of your comparisons. 

For more complex string comparison needs, consider using `strncmp`, which allows you to specify a maximum number of characters to compare, thus providing greater control over the comparison process.

## One Line Summary
The `strcmp` function in C is used to lexicographically compare two strings and return an integer indicating their relationship.