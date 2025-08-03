<!--
Meta Description: # fprintf: A Comprehensive Guide to Formatted Output in C ## Synopsis The `fprintf` function in C is used for formatted output to specified output str...
Meta Keywords: file, output, format, fprintf, specifiers
-->

# fprintf: A Comprehensive Guide to Formatted Output in C

## Synopsis
The `fprintf` function in C is used for formatted output to specified output streams, allowing developers to print data in a controlled and structured manner.

## Documentation

### Purpose
The `fprintf` function is part of the C standard library and is declared in the `stdio.h` header file. It writes formatted data to a specified output stream, such as a file or the standard output (stdout). This function is particularly useful for producing output that conforms to specific formats, making it essential for debugging and logging.

### Usage
The basic syntax of `fprintf` is as follows:

```c
int fprintf(FILE *stream, const char *format, ...);
```

- **Parameters**:
  - `FILE *stream`: A pointer to a `FILE` object that identifies the output stream. This can be a file opened with `fopen` or `stdout` for standard output.
  - `const char *format`: A format string that specifies how subsequent arguments (if any) are converted for output. It can include plain text and format specifiers (like `%d`, `%s`, etc.).
  - `...`: Additional arguments that correspond to the format specifiers in the format string.

- **Return Value**: On success, `fprintf` returns the total number of characters written. On failure, it returns a negative value.

### Details
The format string can contain:
- **Format specifiers**: These begin with a percent sign (`%`) and dictate how to format the corresponding argument. Common specifiers include:
  - `%d` for integers
  - `%f` for floating-point numbers
  - `%s` for strings
  - `%c` for characters
  - `%x` for hexadecimal integers

- **Flags, width, and precision**: You can also include flags (like `-` for left-justification), width (to set the minimum number of characters), and precision (to control the number of digits after the decimal for floating-point numbers).

## Examples

### Basic Example

```c
#include <stdio.h>

int main() {
    int age = 25;
    float height = 5.9;
    char name[] = "Alice";

    fprintf(stdout, "Name: %s, Age: %d, Height: %.1f\n", name, age, height);
    return 0;
}
```

### Writing to a File

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w");
    if (file != NULL) {
        fprintf(file, "This is a test: %d, %.2f\n", 42, 3.14159);
        fclose(file);
    } else {
        perror("Failed to open file");
    }
    return 0;
}
```

## Explanation

### Common Pitfalls
- **Unmatched format specifiers**: Ensure that the number of arguments passed matches the number of format specifiers in the format string. Mismatches can lead to undefined behavior.
- **File handling**: Always check if the file pointer returned by `fopen` is `NULL` to avoid dereferencing a null pointer.
- **Buffer overflows**: When using strings, be cautious of buffer sizes to prevent buffer overflow vulnerabilities.

### Additional Notes
- `fprintf` does not perform automatic type conversion; you must provide the correct type for each format specifier.
- For debugging purposes, consider using `stderr` as the output stream to separate error messages from normal output.

## One Line Summary
The `fprintf` function in C enables formatted output to specified streams, providing precise control over how data is represented and displayed.