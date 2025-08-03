<!--
Meta Description: # ftell in C: Understanding File Position Indicators ## Synopsis The `ftell` function in C retrieves the current file position indicator for a specifi...
Meta Keywords: file, position, ftell, stream, current
-->

# ftell in C: Understanding File Position Indicators

## Synopsis
The `ftell` function in C retrieves the current file position indicator for a specified stream, essential for managing file operations effectively.

## Documentation
The `ftell` function is part of the C Standard Library, defined in the `<stdio.h>` header file. It is used to determine the current position of the file pointer in a given file stream. This is particularly useful when working with file I/O operations, as it allows programmers to keep track of where they are in a file, making it easier to read or write data sequentially.

### Purpose
- To obtain the current position of the file pointer in a file stream.
- To assist in file manipulation tasks such as seeking or buffering data.

### Usage
```c
#include <stdio.h>

long ftell(FILE *stream);
```

- **Parameters**: 
  - `stream`: A pointer to a `FILE` object that specifies an input or output stream.
  
- **Return Value**: 
  - On success, `ftell` returns the current file position as a long integer. 
  - If an error occurs, it returns `-1L` and sets the `errno` variable to indicate the error.

### Error Handling
Common reasons for an error include:
- The `stream` provided is not open or is invalid.
- The `stream` is positioned at an end-of-file or has encountered a read/write error.

## Examples

### Example 1: Basic Usage of ftell
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Unable to open file");
        return 1;
    }

    // Move to a specific position
    fseek(file, 10, SEEK_SET);

    // Get the current position
    long position = ftell(file);
    if (position != -1L) {
        printf("Current position: %ld\n", position);
    } else {
        perror("ftell error");
    }

    fclose(file);
    return 0;
}
```

### Example 2: Using ftell After Writing
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w");
    if (file == NULL) {
        perror("Unable to open file");
        return 1;
    }

    fprintf(file, "Hello, World!");
    
    // Get the position after writing
    long position = ftell(file);
    if (position != -1L) {
        printf("Current position after writing: %ld\n", position);
    } else {
        perror("ftell error");
    }

    fclose(file);
    return 0;
}
```

## Explanation
When using `ftell`, it's important to remember:
- The position returned by `ftell` is in bytes from the beginning of the file.
- If `ftell` is called on a file stream that is not open for reading or writing, it will return `-1L`.
- After `fseek` operations, it's good practice to check the result of `ftell` to confirm that the file pointer has moved as expected.

### Common Pitfalls
- Forgetting to include `<stdio.h>`, which will result in compilation errors.
- Failing to check if the file pointer is valid before calling `ftell`, leading to unexpected errors.
- Mixing binary and text modes can cause discrepancies in reported positions due to newline translations.

## One Line Summary
The `ftell` function in C is used to obtain the current position of the file pointer in a specified file stream, facilitating effective file management.