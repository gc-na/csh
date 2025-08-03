<!--
Meta Description: # strcat: String Concatenation in C Programming ## Synopsis The `strcat` function in C is used to concatenate two strings, appending the contents of o...
Meta Keywords: string, strcat, dest, strings, destination
-->

# strcat: String Concatenation in C Programming

## Synopsis
The `strcat` function in C is used to concatenate two strings, appending the contents of one string to the end of another. It is a part of the C standard library, defined in `<string.h>`.

## Documentation
### Purpose
The primary purpose of `strcat` is to combine two null-terminated strings into a single string. The function appends the source string (second argument) to the destination string (first argument).

### Usage
To use `strcat`, you need to include the `<string.h>` header file. The function signature is as follows:

```c
char *strcat(char *dest, const char *src);
```

- `dest`: A pointer to the destination string that will hold the concatenated result. It must have enough space to hold the resulting string.
- `src`: A pointer to the source string that will be appended to the destination string.

### Return Value
The `strcat` function returns a pointer to the destination string `dest`.

### Important Note
Ensure that the destination string has enough space to accommodate the combined length of both strings, including the null terminator. Otherwise, it may lead to buffer overflow and undefined behavior.

## Examples
### Basic Example
Here is a simple example demonstrating the use of `strcat`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20] = "Hello, ";
    char src[] = "World!";
    
    strcat(dest, src);
    printf("%s\n", dest); // Output: Hello, World!

    return 0;
}
```

### Example with Insufficient Buffer
This example demonstrates a potential pitfall of using `strcat` with insufficient buffer space:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[10] = "Hello";
    char src[] = "World!";
    
    // Unsafe: Not enough space in dest
    strcat(dest, src); 
    printf("%s\n", dest); // Undefined behavior

    return 0;
}
```

## Explanation
### Common Pitfalls
- **Buffer Overflow**: The most critical issue when using `strcat` is ensuring that the destination buffer is large enough to hold the combined strings. If `dest` does not have sufficient space, it may lead to memory corruption and undefined behavior.
  
- **Null Terminator**: The `strcat` function expects both strings to be null-terminated. Failure to null-terminate the strings properly can lead to unexpected results.

- **Overlapping Strings**: The behavior of `strcat` is undefined if the source and destination strings overlap. Always ensure that they do not point to the same memory area.

### Additional Notes
- For safer string concatenation, consider using `strncat`, which allows you to specify the maximum number of characters to append, thus helping to prevent buffer overflows.
- Always initialize your strings to avoid unintended behavior when using string manipulation functions.

## One Line Summary
The `strcat` function in C appends one null-terminated string to another, but caution is needed to avoid buffer overflow and undefined behavior.