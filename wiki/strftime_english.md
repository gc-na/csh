<!--
Meta Description: # strftime: Formatting Date and Time in C ## Synopsis The `strftime` function in C is a standard library function used to format date and time into a ...
Meta Keywords: format, time, string, strftime, date
-->

# strftime: Formatting Date and Time in C

## Synopsis
The `strftime` function in C is a standard library function used to format date and time into a human-readable string based on specified format specifiers.

## Documentation
### Purpose
The `strftime` function is part of the `<time.h>` header file in C. It is designed to convert date and time information stored in a `struct tm` into a formatted string. This is particularly useful for displaying dates and times in a user-friendly format.

### Usage
The function signature of `strftime` is as follows:

```c
size_t strftime(char *s, size_t max, const char *format, const struct tm *tm);
```

- **Parameters**:
  - `char *s`: Pointer to the destination string where the formatted date and time will be stored.
  - `size_t max`: The maximum number of characters to be written to the output string (including the null terminator).
  - `const char *format`: A format string that specifies how to format the date and time. It contains various format specifiers.
  - `const struct tm *tm`: Pointer to a `struct tm` that contains the broken-down time.

- **Return Value**: 
  The function returns the number of characters placed in the output string `s`, not including the null terminator. If the output string is too small to hold the result, `0` is returned.

### Format Specifiers
Common format specifiers used in the `format` string include:
- `%Y`: Year with century (e.g., 2023)
- `%m`: Month as a decimal number (01 to 12)
- `%d`: Day of the month (01 to 31)
- `%H`: Hour in 24-hour format (00 to 23)
- `%M`: Minute (00 to 59)
- `%S`: Second (00 to 59)
- `%a`: Abbreviated weekday name (e.g., Mon)
- `%A`: Full weekday name (e.g., Monday)

## Examples

### Example 1: Basic Usage
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    char buffer[80];

    strftime(buffer, sizeof(buffer), "%Y-%m-%d %H:%M:%S", tm_info);
    printf("Current date and time: %s\n", buffer);

    return 0;
}
```

### Example 2: Custom Formatting
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm tm_info = {0};
    tm_info.tm_year = 2023 - 1900; // Year since 1900
    tm_info.tm_mon = 8 - 1;        // Month from 0 to 11
    tm_info.tm_mday = 15;          // Day of the month
    char buffer[80];

    strftime(buffer, sizeof(buffer), "Date: %A, %B %d, %Y", &tm_info);
    printf("%s\n", buffer); // Output: Date: Friday, August 15, 2023

    return 0;
}
```

## Explanation
When using `strftime`, developers should keep the following points in mind:
- Ensure that the destination buffer is large enough to hold the formatted string. If it is too small, `strftime` will return `0`, and the string will remain unchanged.
- Be aware of the limitations of the format specifiers and the locale settings. The output may vary based on the system locale, particularly for weekday and month names.
- The year in `struct tm` is given as years since 1900, and the month is indexed from 0 (January) to 11 (December).

## One Line Summary
The `strftime` function formats date and time from a `struct tm` into a customizable string representation in C.