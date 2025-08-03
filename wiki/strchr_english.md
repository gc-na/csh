<!--
Meta Description: # The strchr Function in C: A Comprehensive Guide ## Synopsis The `strchr` function in C is a standard library function used to locate the first occur...
Meta Keywords: character, string, strchr, pointer, null
-->

# The strchr Function in C: A Comprehensive Guide

## Synopsis
The `strchr` function in C is a standard library function used to locate the first occurrence of a character in a string. It is essential for string manipulation and searching operations in C programming.

## Documentation

### Purpose
The `strchr` function is part of the C Standard Library, included in the `<string.h>` header file. It is designed to search for a specified character within a given string and return a pointer to the first occurrence of that character. If the character is not found, it returns `NULL`.

### Usage
The function prototype for `strchr` is as follows:
```c
char *strchr(const char *str, int character);
```

#### Parameters
- **str**: A pointer to a null-terminated string in which to search for the character.
- **character**: The character to search for, passed as an `int`, which is typically cast from a `char`.

#### Return Value
- Returns a pointer to the first occurrence of `character` in the string `str`.
- Returns `NULL` if the character is not found.

### Example
Here is a basic example demonstrating how to use `strchr`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *string = "Hello, World!";
    char ch = 'o';
    
    // Use strchr to find the first occurrence of 'o'
    char *result = strchr(string, ch);
    
    if (result != NULL) {
        printf("Character '%c' found at position: %ld\n", ch, result - string);
    } else {
        printf("Character '%c' not found.\n", ch);
    }
    
    return 0;
}
```

### Explanation
While `strchr` is straightforward to use, there are a few common pitfalls and considerations:

- **Null Terminator**: The search includes the null terminator `\0`. If the character being searched for is `\0`, `strchr` will return a pointer to the end of the string.
  
- **Character Type**: The `character` parameter is passed as an `int`, which can sometimes lead to confusion. Ensure that the character is properly cast from `char` to `int` when necessary.

- **Pointer Arithmetic**: The return value of `strchr` is a pointer to the found character. To determine its position, subtract the base pointer of the string from the returned pointer.

- **Return Value Handling**: Always check the return value for `NULL` to avoid dereferencing a null pointer, which can lead to undefined behavior.

## One Line Summary
The `strchr` function in C efficiently locates the first occurrence of a specified character in a string, returning a pointer or `NULL` if not found.