<!--
Meta Description: # strrchr 函数在 C 语言中的使用 ## 摘要 `strrchr` 是 C 语言标准库中的一个字符串处理函数，它用于查找字符串中最后一个出现的指定字符。 ## 文档 ### 目的 `strrchr` 函数用于在给定的字符串中查找最近一次出现的特定字符，并返回指向该字符及其后续部分的指针。如...
Meta Keywords: strrchr, char, str, int, include
-->

# strrchr 函数在 C 语言中的使用

## 摘要
`strrchr` 是 C 语言标准库中的一个字符串处理函数，它用于查找字符串中最后一个出现的指定字符。

## 文档
### 目的
`strrchr` 函数用于在给定的字符串中查找最近一次出现的特定字符，并返回指向该字符及其后续部分的指针。如果未找到该字符，则返回 `NULL`。

### 用法
`strrchr` 的函数原型如下：
```c
char *strrchr(const char *str, int c);
```

- **参数**：
  - `str`：要搜索的字符串。
  - `c`：要查找的字符（作为 `int` 类型传入，但实际上会被当作 `char` 处理）。

- **返回值**：
  - 返回指向最后一个匹配字符的指针，如果未找到，则返回 `NULL`。

### 头文件
要使用 `strrchr` 函数，需要包含以下头文件：
```c
#include <string.h>
```

## 示例
以下是 `strrchr` 函数的基本用法示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "hello world";
    char c = 'o';
    
    char *result = strrchr(str, c);
    if (result) {
        printf("最后一个 '%c' 出现在: %s\n", c, result);
    } else {
        printf("字符 '%c' 未找到。\n", c);
    }
    
    return 0;
}
```

### 输出
```
最后一个 'o' 出现在: o world
```

## 说明
- **注意事项**：
  - `strrchr` 处理的是 `char` 类型的字符，因此在调用时可以直接传入字符常量，例如 `'o'`。
  - 当 `c` 参数为 `'\0'`（空字符）时，`strrchr` 将返回字符串结束位置的指针。

- **常见陷阱**：
  - 确保传入的字符串以 `\0` 结尾，否则可能导致未定义行为。
  - 在使用返回的指针时，不要尝试改变其内容，因为它指向的是字符串字面量的内存区域。

## 一句话总结
`strrchr` 函数用于查找字符串中最后一次出现的指定字符，并返回该字符的指针。