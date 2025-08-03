<!--
Meta Description: # fscanf: A Comprehensive Guide to Formatted Input in C ## Synopsis `fscanf` is a standard library function in C that reads formatted input from a fil...
Meta Keywords: file, fscanf, input, data, format
-->

# fscanf: A Comprehensive Guide to Formatted Input in C

## Synopsis
`fscanf` is a standard library function in C that reads formatted input from a file stream, allowing developers to extract data in a structured way.

## Documentation

### Purpose
The `fscanf` function is used to read data from a file stream and store it into specified variables according to a predefined format. It is particularly useful for parsing structured data, such as configuration files or text input with defined delimiters.

### Usage
The prototype of `fscanf` is as follows:

```c
int fscanf(FILE *stream, const char *format, ...);
```

#### Parameters:
- **`stream`:** A pointer to a `FILE` object that identifies the input stream. This is typically obtained from functions like `fopen`.
- **`format`:** A C string that specifies the format of the input data. It contains conversion specifiers (like `%d`, `%s`, etc.) that dictate how the input should be interpreted.
- **`...`:** A variable number of arguments that correspond to the format specifiers in the `format` string. These arguments must be pointers to the variables where the read data will be stored.

#### Return Value:
The function returns the number of input items successfully matched and assigned, which can be less than the number of items requested or even zero in case of an error or if the end of the file is reached. If an error occurs, `EOF` is returned.

### Example
Here's a simple example demonstrating the use of `fscanf`:

```c
#include <stdio.h>

int main() {
    FILE *file;
    int age;
    char name[50];

    file = fopen("data.txt", "r");
    if (file == NULL) {
        perror("Unable to open file!");
        return 1;
    }

    fscanf(file, "%s %d", name, &age);
    printf("Name: %s, Age: %d\n", name, age);

    fclose(file);
    return 0;
}
```

### Explanation
While `fscanf` is powerful, it is essential to be aware of common pitfalls:

1. **Buffer Overflow:** When reading strings, ensure that the buffer is large enough to hold the input. Use the width modifier in the format string to prevent overflow (e.g., `%49s` for a 50-byte array).
   
2. **Input Validation:** Always check the return value of `fscanf` to ensure that the expected number of items was successfully read. This helps to avoid undefined behavior from using uninitialized variables.

3. **Whitespace Handling:** `fscanf` skips whitespace by default, which can lead to unexpected results when reading formatted data. Be cautious when using it for mixed data types.

4. **End-of-file and Errors:** Handle the possibility of reaching the end of the file or encountering an input error gracefully to avoid crashes or undefined behavior.

5. **Format Specifiers:** Use the correct format specifiers for the data types being read. Mismatched formats can lead to incorrect data being stored or runtime errors.

## One Line Summary
`fscanf` is a C function that reads formatted data from a file stream, allowing for structured input handling.