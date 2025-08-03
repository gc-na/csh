<!--
Meta Description: # fwrite in C: A Comprehensive Guide to File Writing Operations ## Synopsis The `fwrite` function in C is used to write binary data to a file, enablin...
Meta Keywords: file, data, fwrite, writing, function
-->

# fwrite in C: A Comprehensive Guide to File Writing Operations

## Synopsis
The `fwrite` function in C is used to write binary data to a file, enabling efficient handling of data streams directly from memory.

## Documentation

### Purpose
The `fwrite` function is a standard library function defined in `<stdio.h>`, used for writing blocks of data from an array to a file. It is particularly useful for writing binary files or large data structures.

### Usage
The function prototype for `fwrite` is as follows:

```c
size_t fwrite(const void *ptr, size_t size, size_t count, FILE *stream);
```

- **ptr**: A pointer to the array of elements to be written.
- **size**: The size in bytes of each element.
- **count**: The number of elements to write.
- **stream**: A pointer to a `FILE` object that specifies an output stream.

### Return Value
The function returns the total number of elements successfully written, which may be less than `count` if an error occurs or the end of the file is reached. If this value is different from `count`, it indicates that not all requested data was written.

## Examples

### Basic Usage Example 1: Writing an Array of Integers
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("numbers.bin", "wb");
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }

    int numbers[] = {1, 2, 3, 4, 5};
    size_t written = fwrite(numbers, sizeof(int), 5, file);
    
    if (written < 5) {
        perror("Error writing to file");
    }

    fclose(file);
    return 0;
}
```

### Basic Usage Example 2: Writing a Structure
```c
#include <stdio.h>

typedef struct {
    int id;
    char name[20];
} Record;

int main() {
    FILE *file = fopen("records.bin", "wb");
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }

    Record record = {1, "Sample"};
    fwrite(&record, sizeof(Record), 1, file);
    
    fclose(file);
    return 0;
}
```

## Explanation
### Common Pitfalls
1. **File Not Opened**: Ensure that the file is successfully opened in write mode (`"wb"`). Check for `NULL` pointer after `fopen`.
2. **Error Handling**: Always check the return value of `fwrite` to handle partial writes or errors effectively.
3. **Binary vs. Text Mode**: When writing binary data, always open the file in binary mode (use `"wb"`). Failing to do so can lead to data corruption, especially on Windows where newline translation occurs in text mode.
4. **Data Alignment**: Be cautious about the alignment of data structures. If portability is a concern, consider using standardized data formats.

### Additional Notes
- The `fwrite` function does not automatically flush the output buffer to disk. To ensure that all data is written, use `fflush()` or close the file with `fclose()`.
- For large data transfers, consider buffering strategies to improve performance.

## One Line Summary
The `fwrite` function in C efficiently writes binary data from memory to a file stream, enabling direct manipulation of data structures in file operations.