<!--
Meta Description: # Understanding `strstr`: The C Function for String Searching ## Synopsis The `strstr` function in C is a standard library function that locates the f...
Meta Keywords: strstr, string, substring, haystack, needle
-->

# Understanding `strstr`: The C Function for String Searching

## Synopsis
The `strstr` function in C is a standard library function that locates the first occurrence of a substring within a string, returning a pointer to the beginning of the found substring.

## Documentation

### Purpose
The `strstr` function is designed to search for a specific substring within a larger string. It is part of the C Standard Library and is included in the `<string.h>` header file. This function is particularly useful in text processing tasks, where identifying the presence of certain segments within strings is essential.

### Usage
The function prototype for `strstr` is as follows:

```c
char *strstr(const char *haystack, const char *needle);
```

- **Parameters**:
  - `haystack`: A pointer to the null-terminated string to be searched.
  - `needle`: A pointer to the null-terminated substring to be located.

- **Return Value**: 
  - If the substring is found, `strstr` returns a pointer to the first occurrence of the substring within the string (`haystack`).
  - If the substring is not found or if `needle` is an empty string, it returns `NULL`.

### Example
Here are some basic examples demonstrating the use of `strstr`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Hello, welcome to the world of C programming.";
    const char *needle = "welcome";

    char *result = strstr(haystack, needle);
    if (result) {
        printf("Found substring at: %s\n", result);
    } else {
        printf("Substring not found.\n");
    }

    return 0;
}
```

In this example, the output will be:
```
Found substring at: welcome to the world of C programming.
```

### Explanation
While using `strstr`, there are some common pitfalls and considerations to keep in mind:

1. **Case Sensitivity**: The search performed by `strstr` is case-sensitive. For example, searching for "Hello" will not match "hello".

2. **Empty Substring**: Calling `strstr` with an empty `needle` will always return the `haystack`, since an empty string is considered to be present at the start of any string.

3. **Null Pointers**: Passing a `NULL` pointer for either the `haystack` or `needle` will lead to undefined behavior. Always ensure both strings are valid.

4. **Performance**: The time complexity of `strstr` in the worst case is O(n*m), where n is the length of the `haystack` and m is the length of the `needle`. For very large strings, consider optimizing or using more advanced algorithms if performance becomes an issue.

5. **Modifications**: Be cautious when modifying the `haystack` string after calling `strstr`. The returned pointer points to the original string, and altering it can lead to undefined behavior.

## One Line Summary
The `strstr` function in C searches for the first occurrence of a substring within a string, returning a pointer to that position or `NULL` if not found.