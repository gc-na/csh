<!--
Meta Description: # Rewind in C: Understanding the rewind() Function ## Synopsis The `rewind()` function in C is a standard library function used to reset the file posi...
Meta Keywords: file, rewind, buffer, read, function
-->

# Rewind in C: Understanding the rewind() Function

## Synopsis
The `rewind()` function in C is a standard library function used to reset the file position indicator of a given file stream to the beginning of the file. This is particularly useful when you need to read or write to a file from the start after performing operations that moved the file pointer.

## Documentation
### Purpose
The `rewind()` function is part of the C standard I/O library and is defined in the `<stdio.h>` header file. Its primary purpose is to set the file position indicator of a file stream back to the beginning. This allows subsequent read or write operations to start from the start of the file.

### Usage
The syntax for the `rewind()` function is as follows:

```c
#include <stdio.h>

void rewind(FILE *stream);
```

- **stream**: A pointer to a `FILE` object that identifies the stream you want to rewind.

### Details
- After calling `rewind()`, the file position indicator is set to the start of the file.
- If the file is opened in read mode, any subsequent read operations will begin from the start.
- If the file is opened in write mode, the file will be cleared, and subsequent writes will start from the beginning.
- The `rewind()` function does not return a value, and it does not signal an error (unlike `fseek()`, which returns an integer).

## Examples
Here are some basic usage examples of the `rewind()` function:

### Example 1: Rewinding a File for Reading
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Error opening file");
        return -1;
    }

    // Read the first line
    char buffer[100];
    fgets(buffer, sizeof(buffer), file);
    printf("First read: %s", buffer);

    // Rewind the file to the start
    rewind(file);

    // Read the first line again
    fgets(buffer, sizeof(buffer), file);
    printf("After rewind: %s", buffer);

    fclose(file);
    return 0;
}
```

### Example 2: Rewinding a File for Writing
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w+");
    if (file == NULL) {
        perror("Error opening file");
        return -1;
    }

    // Write to the file
    fprintf(file, "Hello, World!\n");

    // Rewind the file for reading
    rewind(file);

    // Read from the file
    char buffer[100];
    fgets(buffer, sizeof(buffer), file);
    printf("Read from file: %s", buffer);

    fclose(file);
    return 0;
}
```

## Explanation
### Common Pitfalls
- **File Mode**: Ensure the file is opened in an appropriate mode. Using `rewind()` on a file not opened for reading will lead to undefined behavior.
- **Error Checking**: Always check if the file has been opened successfully before attempting to rewind.
- **Buffer Management**: If the file is modified (e.g., data written) after rewinding, ensure that the buffer is properly managed to avoid reading stale data.

### Additional Notes
- `rewind()` is often more straightforward than using `fseek(stream, 0, SEEK_SET)`, as it does not require calculating offsets.
- It is a good practice to use `rewind()` when you need to reset your file pointer before re-reading or re-writing, especially in loops or multiple operations.

## One Line Summary
The `rewind()` function in C resets the file position indicator to the beginning of a specified file stream, enabling fresh read or write operations.