<!--
Meta Description: # Understanding `realloc`: Dynamic Memory Management in C ## Synopsis The `realloc` function in C is used to resize a previously allocated memory bloc...
Meta Keywords: memory, realloc, block, pointer, null
-->

# Understanding `realloc`: Dynamic Memory Management in C

## Synopsis
The `realloc` function in C is used to resize a previously allocated memory block, allowing for dynamic memory management and efficient use of resources.

## Documentation

### Purpose
The `realloc` function is part of the C standard library and is included in the `<stdlib.h>` header file. Its primary purpose is to resize a memory block that was previously allocated using `malloc`, `calloc`, or `realloc`.

### Usage
The function prototype for `realloc` is as follows:

```c
void* realloc(void* ptr, size_t new_size);
```

- **Parameters**:
  - `ptr`: A pointer to the memory block that you want to resize. If this pointer is `NULL`, `realloc` behaves like `malloc` and allocates a new block of memory.
  - `new_size`: The new size for the memory block in bytes. If `new_size` is zero and `ptr` is not `NULL`, the memory block is freed.

- **Return Value**: 
  - On success, `realloc` returns a pointer to the resized memory block. This pointer may be the same as `ptr`, or it may point to a new memory location.
  - If the resizing fails (due to insufficient memory), it returns `NULL`, and the original memory block remains unchanged.

### Details
- When resizing, if the new size is larger than the current size, `realloc` may need to allocate a new block of memory and copy the contents from the old block to the new one.
- If the new size is smaller, the memory block is shrunk, and the excess memory is freed.
- Always check the returned pointer to avoid memory leaks or dereferencing `NULL`.

## Examples

### Basic Usage Example
Here is a simple example demonstrating how to use `realloc`:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Allocate initial memory
    int* arr = (int*)malloc(5 * sizeof(int));
    if (arr == NULL) {
        perror("Failed to allocate memory");
        return EXIT_FAILURE;
    }

    // Fill the array
    for (int i = 0; i < 5; i++) {
        arr[i] = i + 1;
    }

    // Resize the array
    int* new_arr = (int*)realloc(arr, 10 * sizeof(int));
    if (new_arr == NULL) {
        free(arr); // Free the old memory if realloc fails
        perror("Failed to reallocate memory");
        return EXIT_FAILURE;
    }
    arr = new_arr; // Update pointer to the new memory location

    // Fill the new elements
    for (int i = 5; i < 10; i++) {
        arr[i] = i + 1;
    }

    // Print the array
    for (int i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // Free the memory
    free(arr);
    return EXIT_SUCCESS;
}
```

## Explanation

### Common Pitfalls
1. **Failure to Check Return Value**: Always check if `realloc` returns `NULL` to avoid dereferencing a null pointer, which leads to undefined behavior.
2. **Memory Leaks**: If you do not assign the result of `realloc` back to your original pointer and `realloc` fails, you will lose the reference to the original memory block, leading to a memory leak.
3. **Using Invalid Pointers**: Ensure that the pointer passed to `realloc` was previously allocated with memory management functions (`malloc`, `calloc`, or `realloc`).

### Additional Notes
- If you pass a `NULL` pointer, `realloc` behaves like `malloc`, allocating a new block of memory.
- It is generally a good practice to initialize your pointers to `NULL`, as it makes it easier to check if they point to valid memory.

## One Line Summary
`realloc` is a C library function that resizes a previously allocated memory block, allowing for dynamic memory management.