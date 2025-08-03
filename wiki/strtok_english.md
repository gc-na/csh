<!--
Meta Description: # Understanding `strtok`: Tokenization in C Programming ## Synopsis `strtok` is a standard library function in C used for splitting a string into a se...
Meta Keywords: string, strtok, null, function, delimiters
-->

# Understanding `strtok`: Tokenization in C Programming

## Synopsis
`strtok` is a standard library function in C used for splitting a string into a series of tokens based on specified delimiters. This function is essential for parsing strings in various applications like data processing, natural language processing, and more.

## Documentation
### Purpose
The `strtok` function is designed to tokenize a string, allowing developers to break down strings into smaller, manageable parts (tokens) based on specified delimiters, such as spaces, commas, or any other characters.

### Usage
The function is defined in the `<string.h>` header and has the following prototype:

```c
char *strtok(char *str, const char *delim);
```

### Parameters
- **str**: The string to be tokenized. On the first call, this should be the target string. On subsequent calls, this parameter should be `NULL`.
- **delim**: A string containing all the delimiter characters. The `strtok` function will use these characters to determine where to split the string.

### Return Value
`strtok` returns a pointer to the first token found in the string. If no tokens are found or the input string is `NULL`, it returns `NULL`.

### Notes
- `strtok` modifies the original string by inserting null characters (`'\0'`) at the position of the delimiters.
- It is not thread-safe since it uses static storage to hold the current position of the string being tokenized.

## Examples
### Basic Usage Example
Here’s a simple example demonstrating how to use `strtok` to split a string by spaces:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello, World! Welcome to C programming.";
    const char delim[] = " ,.!";

    char *token = strtok(str, delim);
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, delim);
    }

    return 0;
}
```

### Output
```
Hello
World
Welcome
to
C
programming
```

## Explanation
### Common Pitfalls and Gotchas
1. **Modifying the Original String**: Since `strtok` alters the input string, it is essential to work on a copy if the original string is needed later.
2. **Subsequent Calls**: Always pass `NULL` for the first argument in subsequent calls to continue tokenization on the same string.
3. **Thread Safety**: For thread-safe tokenization, consider using `strtok_r`, which is a reentrant version of `strtok`.
4. **Multiple Delimiters**: If multiple delimiters are adjacent, `strtok` will treat them as one and skip empty tokens.

## One Line Summary
`strtok` is a C function used for splitting strings into tokens based on specified delimiters, modifying the original string in the process.