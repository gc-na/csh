<!--
Meta Description: # Understanding `feof` in C: Checking for End-of-File ## Synopsis The `feof` function in C is used to determine if the end of a file has been reached ...
Meta Keywords: file, feof, end, read, reached
-->

# Understanding `feof` in C: Checking for End-of-File

## Synopsis
The `feof` function in C is used to determine if the end of a file has been reached during file reading operations, providing a way to prevent reading beyond the file's contents.

## Documentation
`feof` is a standard library function declared in the `<stdio.h>` header file. It checks the end-of-file indicator for a given file stream. When a file stream reaches the end of a file, this indicator is set, allowing programs to respond appropriately.

### Purpose
The primary purpose of `feof` is to assist developers in managing file input operations safely by indicating whether the end of a file has been reached, thereby preventing potential errors that could occur if an attempt is made to read past the file's content.

### Usage
The syntax for `feof` is as follows:

```c
int feof(FILE *stream);
```

- **Parameters**: 
  - `stream`: A pointer to the `FILE` object that identifies the stream being checked.
  
- **Return Value**: 
  - Returns a non-zero value (true) if the end of the file has been reached; otherwise, it returns 0 (false).

### Example
Here is a simple example demonstrating how to use `feof`:

```c
#include <stdio.h>

int main() {
    FILE *file;
    char buffer[100];

    file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Error opening file");
        return -1;
    }

    while (fgets(buffer, sizeof(buffer), file) != NULL) {
        printf("%s", buffer);
    }

    if (feof(file)) {
        printf("End of file reached.\n");
    }

    fclose(file);
    return 0;
}
```

In this example, we open a file named `example.txt`, read it line by line using `fgets`, and check for the end of the file with `feof`.

## Explanation
While `feof` is a straightforward function, there are common pitfalls associated with its usage:

- **Check After Reading**: Always check `feof` after an attempt to read from the file. If you call `feof` before attempting a read operation, it will not indicate whether the end of the file has been reached.

- **Buffered I/O**: The end-of-file indicator is set only after an attempt to read past the end of the file. Therefore, you may not see the effect of `feof` until after a read function fails.

- **Error Handling**: Using `feof` alone is not sufficient for error handling. It's important to also check `ferror` to determine if the read operation failed due to an error, as opposed to reaching the end of the file.

## One Line Summary
The `feof` function in C is used to check if the end of a file has been reached, helping to manage file reading operations safely.