<!--
Meta Description: # Understanding `__LINE__` in C: A Preprocessor Directive for Line Number Tracking ## Synopsis `__LINE__` is a predefined macro in C that provides the...
Meta Keywords: __line__, line, code, number, macro
-->

# Understanding `__LINE__` in C: A Preprocessor Directive for Line Number Tracking

## Synopsis
`__LINE__` is a predefined macro in C that provides the current line number of the source code file during compilation. It is a powerful tool for debugging and logging, enabling developers to track the exact location of code within the source files.

## Documentation
The `__LINE__` macro is a feature of the C preprocessor, which is invoked before the actual compilation of the code. It expands to an integer constant that represents the current line number in the source code file. This macro can be useful for debugging purposes, as it allows developers to insert line numbers into error messages, logs, or assertions, thereby facilitating easier tracking of issues.

### Purpose
- To obtain the current line number of the code being compiled.
- To assist in debugging by providing contextual information about where an error or log message originates.

### Usage
The `__LINE__` macro is used without any parameters and can be included in any part of the code. It is commonly used in conjunction with preprocessor directives like `#error`, `#warning`, and logging functions.

### Details
- **Type**: Integer constant.
- **Scope**: It is evaluated in the context of the current source file, and its value changes as the code progresses through lines.
- **Standard Compliance**: `__LINE__` is part of the C standard, ensuring consistency across different compilers.

## Examples
Here are a few simple examples demonstrating the usage of `__LINE__` in C code:

### Example 1: Basic Use in Logging
```c
#include <stdio.h>

void logMessage(const char *message) {
    printf("Log: %s (Line: %d)\n", message, __LINE__);
}

int main() {
    logMessage("Program started");
    // More code here...
    return 0;
}
```

### Example 2: Using with Preprocessor Directives
```c
#include <stdio.h>

#define ERROR(msg) printf("Error: %s (File: %s, Line: %d)\n", msg, __FILE__, __LINE__)

int main() {
    ERROR("Something went wrong!");
    return 0;
}
```

### Example 3: Conditional Compilation
```c
#include <stdio.h>

int main() {
    #if DEBUG
        printf("Debugging information (Line: %d)\n", __LINE__);
    #endif
    return 0;
}
```

## Explanation
While `__LINE__` is straightforward to use, there are a few common pitfalls to be aware of:

- **Line Number Changes**: If you add or remove lines of code, the value of `__LINE__` will change accordingly. This can lead to confusion if not properly managed.
- **Macro Expansion**: When used within macros, the value of `__LINE__` will reflect the line number of the macro invocation rather than the line number inside the macro body itself.
- **Readability**: Overusing `__LINE__` may clutter the code, making it less readable. It's best used judiciously in critical areas, such as error logging.

## One Line Summary
`__LINE__` is a predefined macro in C that provides the current line number of the source code file, aiding in debugging and logging.