<!--
Meta Description: # Understanding `ferror` in C: Error Handling for File Streams ## Synopsis The `ferror` function in C is a standard library function used to check for...
Meta Keywords: file, error, ferror, errors, stream
-->

# Understanding `ferror` in C: Error Handling for File Streams

## Synopsis
The `ferror` function in C is a standard library function used to check for errors on file streams, allowing programmers to handle file I/O errors gracefully.

## Documentation
### Purpose
The `ferror` function is used to determine if an error occurred during a previous file operation on a specified file stream. It is part of the C standard library and defined in the `<stdio.h>` header. This function plays a critical role in error detection when performing file operations, enabling developers to take appropriate actions when an error is encountered.

### Usage
The syntax for `ferror` is as follows:
```c
int ferror(FILE *stream);
```
- **Parameters**: 
  - `stream`: A pointer to a `FILE` object that identifies the stream to be checked for errors.
  
- **Return Value**: 
  - The function returns a non-zero value if an error has occurred on the stream; otherwise, it returns zero.

### Details
To use `ferror`, follow these steps:
1. Open a file using functions like `fopen`.
2. Perform file operations (e.g., `fread`, `fwrite`, `fprintf`).
3. After operations, check for errors using `ferror`.
4. If `ferror` returns a non-zero value, handle the error appropriately.

Example of including `<stdio.h>`:
```c
#include <stdio.h>
```

## Examples
Here are some basic usage examples of `ferror`:

### Example 1: Checking for Errors After Writing
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "w");
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }

    // Attempt to write to file
    if (fprintf(file, "Hello, World!\n") < 0) {
        if (ferror(file)) {
            perror("Error writing to file");
        }
    }

    fclose(file);
    return 0;
}
```

### Example 2: Checking for Errors After Reading
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }

    char buffer[256];
    if (fgets(buffer, sizeof(buffer), file) == NULL) {
        if (ferror(file)) {
            perror("Error reading from file");
        }
    }

    fclose(file);
    return 0;
}
```

## Explanation
When using `ferror`, keep in mind the following common pitfalls and notes:
- **Uncleared Error State**: Once an error is detected, the error state remains set until it is cleared using `clearerr(stream)`. If you check `ferror` multiple times without clearing the error state, it will continue to return non-zero.
- **File State Management**: Always ensure the file stream is properly opened before checking for errors. Trying to check an unopened stream may lead to undefined behavior.
- **Error Checking Sequence**: It is good practice to check the return values of file operations before invoking `ferror`. This can help to identify the specific operation that caused the error.

## One Line Summary
The `ferror` function in C checks for errors on file streams, aiding in robust file I/O error handling.