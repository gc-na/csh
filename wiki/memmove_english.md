<!--
Meta Description: # Comprehensive Guide to `memmove` in C: Understanding Memory Manipulation ## Synopsis `memmove` is a standard library function in C used for safely c...
Meta Keywords: memmove, buffer, memory, source, destination
-->

# Comprehensive Guide to `memmove` in C: Understanding Memory Manipulation

## Synopsis
`memmove` is a standard library function in C used for safely copying a block of memory from one location to another, allowing for overlapping memory regions.

## Documentation

### Purpose
The `memmove` function is designed to copy a specified number of bytes from a source memory location to a destination memory location. It is particularly useful when the source and destination areas overlap, as it handles these situations correctly by using a temporary buffer.

### Function Prototype
```c
#include <string.h>

void *memmove(void *dest, const void *src, size_t n);
```

### Parameters
- **`dest`**: A pointer to the destination buffer where the content is to be copied.
- **`src`**: A pointer to the source buffer from which content is to be copied.
- **`n`**: The number of bytes to copy from the source to the destination.

### Return Value
`memmove` returns a pointer to the destination (`dest`).

### Behavior
- If the source and destination do not overlap, `memmove` behaves like `memcpy`.
- If they do overlap, `memmove` ensures that the original source bytes are copied before being overwritten.

### Header File
To use `memmove`, include the header file `<string.h>`.

## Examples

### Example 1: Basic Usage
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello, World!";
    memmove(str + 7, str, 5);  // Move "Hello" to the end of the string
    printf("%s\n", str);       // Output: "Hello, Hello!"
    return 0;
}
```

### Example 2: Overlapping Regions
```c
#include <stdio.h>
#include <string.h>

int main() {
    char buffer[] = "123456789";
    memmove(buffer + 3, buffer, 6);  // Move "123456" to overlap with itself
    printf("%s\n", buffer);           // Output: "123123456"
    return 0;
}
```

## Explanation
### Common Pitfalls
- **Incorrect Buffer Sizes**: Ensure that the destination buffer is large enough to hold the copied data, or it may lead to buffer overflows.
- **Null Pointers**: Passing null pointers for `src` or `dest` can lead to undefined behavior. Always validate pointers before using `memmove`.
- **Zero Length**: If `n` is zero, `memmove` will do nothing, which is valid but may sometimes lead to confusion if not properly handled.

### Additional Notes
- `memmove` is often less efficient than `memcpy` due to the overhead of handling overlapping regions. Use `memcpy` when you are certain that the memory areas do not overlap for better performance.
- The function is part of the C Standard Library and thus is widely supported across different C compilers and platforms.

## One Line Summary
`memmove` is a C standard library function that safely copies memory between overlapping regions, ensuring the integrity of the source data.