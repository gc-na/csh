<!--
Meta Description: # C语言中的strtok函数详解 ## 概述 `strtok`是C标准库中的一个字符串处理函数，用于将字符串分割成一系列标记（token），常用于解析以特定分隔符分隔的字符串。 ## 文档 ### 目的 `strtok`函数的主要目的是通过指定的分隔符，将一个字符串分割成多个部分。 ### 用法 ...
Meta Keywords: strtok, token, char, delim, null
-->

# C语言中的strtok函数详解

## 概述
`strtok`是C标准库中的一个字符串处理函数，用于将字符串分割成一系列标记（token），常用于解析以特定分隔符分隔的字符串。

## 文档
### 目的
`strtok`函数的主要目的是通过指定的分隔符，将一个字符串分割成多个部分。

### 用法
`strtok`函数的原型如下：
```c
char *strtok(char *str, const char *delim);
```

- **参数**：
  - `str`：要分割的字符串。如果是第一次调用该函数，则传入待分割的字符串；后续调用时应传入`NULL`。
  - `delim`：一个包含所有分隔符的字符串。`strtok`会根据这些分隔符来分割字符串。

- **返回值**：
  - 返回指向下一个标记的指针，如果没有更多的标记，则返回`NULL`。

### 注意事项
- `strtok`会修改原始字符串，将分隔符替换为`'\0'`。
- 该函数不是线程安全的，因为它使用静态内部状态。
- 如果需要在多线程环境中使用分割功能，建议使用`strtok_r`函数。

## 示例
以下是`strtok`函数的基本用法示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "C语言,编程,分割字符串";
    const char *delim = ",";
    char *token;

    // 第一次调用strtok，传入待分割的字符串
    token = strtok(str, delim);

    // 持续调用strtok，传入NULL以获取后续标记
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, delim);
    }

    return 0;
}
```
**输出**：
```
C语言
编程
分割字符串
```

## 说明
- **常见错误**：
  - 在使用`strtok`时，如果传入的字符串是常量字符串（如`"hello,world"`），程序将崩溃，因为该字符串是只读的。
  - 忘记在后续调用中使用`NULL`作为第一个参数，会导致未定义行为。
  
- **额外注意**：
  - `strtok`只适用于简单的分割需求，对于复杂的字符串解析，推荐使用正则表达式或其他更强大的解析工具。

## 一句话总结
`strtok`函数是C语言中用于分割字符串的工具，通过指定分隔符将字符串拆分为多个标记。