<!--
Meta Description: # putc: Writing Characters to a File in C ## Synopsis The `putc` function in C is used to write a single character to a specified output stream. It is...
Meta Keywords: file, putc, character, output, stream
-->

# putc: Writing Characters to a File in C

## Synopsis
The `putc` function in C is used to write a single character to a specified output stream. It is a part of the C standard library and is commonly utilized for file operations.

## Documentation
The `putc` function is defined in the `<stdio.h>` header file and is prototyped as follows:

```c
int putc(int character, FILE *stream);
```

### Purpose
The primary purpose of `putc` is to write a character to a specified file or output stream. It is particularly useful in scenarios where you need to output data character by character.

### Parameters
- **character**: This is the character to be written, passed as an `int`. It is typically provided as a `char`, which is promoted to an `int` when passed to the function.
- **stream**: A pointer to a `FILE` object that identifies the output stream (e.g., `stdout`, a file pointer) where the character will be written.

### Return Value
`putc` returns the character written as an `unsigned char` cast to an `int` or `EOF` if an error occurs.

### Usage
To use `putc`, include the `<stdio.h>` header in your program. Open a file stream using functions such as `fopen`, then call `putc` to write characters to the file or standard output.

## Examples
### Example 1: Writing to Standard Output

```c
#include <stdio.h>

int main() {
    char ch = 'A';
    putc(ch, stdout);  // Writes 'A' to the standard output
    return 0;
}
```

### Example 2: Writing to a File

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w");
    if (file != NULL) {
        putc('H', file); // Writes 'H' to the file
        putc('e', file); // Writes 'e' to the file
        putc('l', file); // Writes 'l' to the file
        putc('l', file); // Writes 'l' to the file
        putc('o', file); // Writes 'o' to the file
        fclose(file);    // Close the file
    }
    return 0;
}
```

## Explanation
While `putc` is a simple and efficient way to write characters, there are a few common pitfalls to be aware of:

1. **Error Handling**: Always check the return value of `putc` to ensure that the character was written successfully. If there is an error, `putc` will return `EOF`.

2. **Buffering**: The output stream may be buffered. This means that characters written with `putc` may not appear in the file immediately. Use `fflush` to flush the buffer if immediate output is necessary.

3. **File Open Modes**: Ensure the file is opened in a mode that allows writing (e.g., "w", "a"). Opening a file in read-only mode will lead to undefined behavior when trying to write.

4. **Character Encoding**: Be mindful of character encoding, especially when dealing with non-ASCII characters. The `putc` function deals with raw bytes, and the interpretation of these bytes depends on the encoding used.

## One Line Summary
`putc` is a C standard library function used to write a single character to a specified output stream, returning the character written or an error indicator.