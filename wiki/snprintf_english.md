<!--
Meta Description: # snprintf in C: A Comprehensive Guide to Safe String Formatting ## Synopsis The `snprintf` function in C safely formats and stores a string in a spec...
Meta Keywords: buffer, snprintf, string, size, written
-->

# snprintf in C: A Comprehensive Guide to Safe String Formatting

## Synopsis
The `snprintf` function in C safely formats and stores a string in a specified buffer, preventing buffer overflow by limiting the number of characters written.

## Documentation
### Purpose
`snprintf` is designed to format a string according to a specified format and store it in a buffer while ensuring that the buffer size is not exceeded. This prevents potential buffer overflow vulnerabilities, making it a safer alternative to traditional string formatting functions like `sprintf`.

### Usage
The function prototype for `snprintf` is as follows:

```c
int snprintf(char *str, size_t size, const char *format, ...);
```

#### Parameters
- `char *str`: A pointer to the destination buffer where the formatted string will be stored.
- `size_t size`: The maximum number of characters to write to the buffer, including the null terminator.
- `const char *format`: A format string that specifies how subsequent arguments (if any) are converted for output.
- `...`: Additional arguments corresponding to the format specifiers in the format string.

#### Return Value
`snprintf` returns the number of characters that would have been written if the buffer were large enough (not including the terminating null byte). If the output was truncated due to size restrictions, the return value will be greater than or equal to `size`.

### Example
Here are a few basic usage examples demonstrating `snprintf`:

```c
#include <stdio.h>

int main() {
    char buffer[50];

    // Example 1: Basic string formatting
    int n = snprintf(buffer, sizeof(buffer), "Hello, %s!", "World");
    printf("%s (written chars: %d)\n", buffer, n);

    // Example 2: Integer formatting
    n = snprintf(buffer, sizeof(buffer), "Number: %d", 42);
    printf("%s (written chars: %d)\n", buffer, n);

    // Example 3: Handling truncation
    n = snprintf(buffer, sizeof(buffer), "This is a very long string that might be truncated!");
    printf("%s (written chars: %d)\n", buffer, n);

    return 0;
}
```

### Explanation
- **Common Pitfalls**: 
  - Failing to allocate enough space for the buffer can lead to truncation of the output. Always ensure that the buffer is sufficiently large for the expected formatted string.
  - Not accounting for the null terminator can lead to unexpected behavior. The specified size includes space for the null terminator, so the effective maximum number of characters that can be written is `size - 1`.

- **Gotchas**:
  - The return value can be misleading if the output is truncated. Always check the return value against `size` to determine whether truncation occurred.
  - Using `snprintf` in a loop without careful buffer management can lead to unexpected results if the buffer is not reset or managed properly between writes.

- **Additional Notes**: 
  - `snprintf` is part of the C standard library and is included in `<stdio.h>`.
  - It is preferable to use `snprintf` over `sprintf` due to its safety features concerning buffer overflow.

## One Line Summary
`snprintf` is a safe string formatting function in C that prevents buffer overflow by limiting the number of characters written to a specified buffer.