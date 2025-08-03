<!--
Meta Description: # Understanding `strrchr`: The C Function for Finding the Last Occurrence of a Character in a String ## Synopsis The `strrchr` function in C is a stan...
Meta Keywords: string, character, strrchr, str, last
-->

# Understanding `strrchr`: The C Function for Finding the Last Occurrence of a Character in a String

## Synopsis
The `strrchr` function in C is a standard library function that is used to locate the last occurrence of a specified character in a given string.

## Documentation

### Purpose
`strrchr` is part of the C Standard Library, declared in the header file `<string.h>`. It is particularly useful for string manipulation tasks, allowing developers to find the last occurrence of a character efficiently.

### Usage
The function prototype for `strrchr` is as follows:

```c
char *strrchr(const char *str, int c);
```

#### Parameters
- `str`: A pointer to the null-terminated string in which to search.
- `c`: The character to search for, passed as an `int` but interpreted as a `char`.

#### Return Value
- Returns a pointer to the last occurrence of the character `c` in the string `str`.
- If the character is not found, it returns `NULL`.

### Requirements
- Include the header file: 
  ```c
  #include <string.h>
  ```

## Examples

### Example 1: Basic Usage
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *last_occurrence = strrchr(str, 'o');

    if (last_occurrence) {
        printf("Last occurrence of 'o': %s\n", last_occurrence);
    } else {
        printf("'o' not found in the string.\n");
    }
    return 0;
}
```

### Example 2: Character Not Found
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *last_occurrence = strrchr(str, 'z');

    if (last_occurrence) {
        printf("Last occurrence of 'z': %s\n", last_occurrence);
    } else {
        printf("'z' not found in the string.\n");
    }
    return 0;
}
```

## Explanation
### Common Pitfalls
- **Null Pointer**: If the input string `str` is a null pointer, the behavior is undefined. Always ensure that the string is valid before calling `strrchr`.
- **Character Interpretation**: The character `c` is passed as an `int`, which allows for the use of character constants (like `'a'`) but may be confusing for beginners. Remember that any character can be passed as an `int`.

### Additional Notes
- The search is case-sensitive. For example, searching for `'a'` will not match `'A'`.
- If the character to find is the null terminator (`'\0'`), `strrchr` will return a pointer to the end of the string.
- If `str` is an empty string (`""`), `strrchr` will return `NULL` unless searching for `'\0'`.

## One Line Summary
`strrchr` is a C function that finds the last occurrence of a specified character in a string, returning a pointer to it or `NULL` if not found.