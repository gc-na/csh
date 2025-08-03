<!--
Meta Description: # strcpy: The C Standard Library String Copy Function ## Synopsis `strcpy` is a function in the C Standard Library used to copy one string (including ...
Meta Keywords: string, strcpy, source, destination, buffer
-->

# strcpy: The C Standard Library String Copy Function

## Synopsis
`strcpy` is a function in the C Standard Library used to copy one string (including the null terminator) to another. It is defined in the `<string.h>` header file and is essential for string manipulation in C programming.

## Documentation

### Purpose
The primary purpose of `strcpy` is to duplicate a string from a source to a destination buffer. This function is widely used for string handling in C programming, allowing developers to manage strings effectively.

### Usage
The function prototype for `strcpy` is as follows:

```c
char *strcpy(char *dest, const char *src);
```

#### Parameters
- `dest`: A pointer to the destination buffer where the string will be copied. This buffer must have enough space to hold the copied string, including the null terminator.
- `src`: A pointer to the source string that will be copied.

#### Return Value
`strcpy` returns a pointer to the destination string (`dest`). If the source string is `NULL`, the behavior is undefined.

### Function Behavior
`strcpy` performs the following actions:
1. Copies characters from the source string (`src`) to the destination buffer (`dest`), one character at a time.
2. Stops copying when it encounters the null terminator (`\0`) in the source string, which is also copied to the destination.

## Examples

### Basic Example
Here’s a simple example demonstrating the use of `strcpy`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char source[] = "Hello, World!";
    char destination[50]; // Ensure sufficient space

    strcpy(destination, source);
    printf("Copied string: %s\n", destination);

    return 0;
}
```

### Example with Overlapping Buffers (Undefined Behavior)
It is important to note that if the source and destination overlap, the behavior of `strcpy` is undefined. For instance:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello, World!";
    
    strcpy(str + 7, str); // Undefined behavior: overlapping buffers
    printf("Result: %s\n", str);

    return 0;
}
```

## Explanation

### Common Pitfalls
- **Buffer Overflow**: One of the most common issues with `strcpy` is not allocating enough space in the destination buffer. If the destination buffer is smaller than the source string, this can lead to buffer overflow, resulting in undefined behavior and potential security vulnerabilities.
  
- **Null Pointer Handling**: Passing a `NULL` pointer as the source (`src`) can cause the program to crash. Always ensure that the source string is valid before calling `strcpy`.

- **Overlapping Buffers**: As mentioned, if the source and destination buffers overlap, the output is unpredictable. Use `memmove` instead if overlapping regions are a concern.

### Additional Notes
- **Alternative Functions**: To avoid buffer overflow risks, consider using `strncpy`, which allows you to specify a maximum number of characters to copy. However, `strncpy` does not guarantee null termination if the source string is longer than the specified length.
  
- **Security Considerations**: Modern C programming practices often recommend safer alternatives to `strcpy` to mitigate risks associated with buffer overflows. Functions like `strlcpy` or `snprintf` are preferred in many applications.

## One Line Summary
`strcpy` is a C standard library function that copies a string from a source to a destination buffer, including the null terminator, but requires careful management of buffer sizes to avoid overflow.