<!--
Meta Description: # memcpy in C: A Comprehensive Guide to Memory Copying ## Synopsis `memcpy` is a standard library function in C that copies a specified number of byte...
Meta Keywords: memcpy, memory, dest, src, destination
-->

# memcpy in C: A Comprehensive Guide to Memory Copying

## Synopsis
`memcpy` is a standard library function in C that copies a specified number of bytes from one memory location to another, making it essential for efficient memory manipulation in various applications.

## Documentation
### Purpose
The `memcpy` function is designed to copy a block of memory from a source address to a destination address. It is a powerful tool for working with arrays, structures, and other data types in C.

### Function Prototype
```c
void *memcpy(void *dest, const void *src, size_t n);
```

### Parameters
- **dest**: A pointer to the destination memory location where the content is to be copied.
- **src**: A pointer to the source memory location from which the content is to be copied.
- **n**: The number of bytes to copy from the source to the destination.

### Return Value
The function returns a pointer to the destination (`dest`).

### Usage
To use `memcpy`, include the header file `<string.h>` in your C program. It is important to ensure that the source and destination memory areas do not overlap, as `memcpy` does not handle overlapping regions safely. For overlapping memory areas, consider using `memmove` instead.

## Examples
### Example 1: Basic Usage
```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[50] = "Hello, World!";
    char dest[50];

    memcpy(dest, src, strlen(src) + 1); // +1 to include the null terminator

    printf("Copied string: %s\n", dest);
    return 0;
}
```

### Example 2: Copying an Array
```c
#include <stdio.h>
#include <string.h>

int main() {
    int src[5] = {1, 2, 3, 4, 5};
    int dest[5];

    memcpy(dest, src, sizeof(src)); // Copy entire array

    printf("Copied array: ");
    for (int i = 0; i < 5; i++) {
        printf("%d ", dest[i]);
    }
    printf("\n");
    return 0;
}
```

## Explanation
### Common Pitfalls
1. **Overlapping Memory Areas**: If the source and destination memory areas overlap, the behavior of `memcpy` is undefined. Use `memmove` in such cases.
2. **Buffer Overflow**: Ensure that the destination buffer is large enough to hold the copied data to avoid buffer overflow vulnerabilities.
3. **Incorrect Size**: Always pass the correct number of bytes to copy. Forgetting to account for the null terminator in strings can lead to unexpected results.

### Additional Notes
- `memcpy` is generally faster than alternatives like `strcpy` when dealing with raw memory, as it operates at the byte level.
- The function does not check for null pointers. Ensure that neither `src` nor `dest` is a null pointer before calling `memcpy`, as this will lead to undefined behavior.

## One Line Summary
`memcpy` is a C standard library function that efficiently copies a specified number of bytes from a source memory location to a destination.