<!--
Meta Description: # strcmp 函数在 C 语言中的使用 ## 概述 `strcmp` 是 C 语言中用于比较两个字符串的标准库函数。它的主要功能是确定两个字符串的字典顺序关系。 ## 文档 ### 目的 `strcmp` 函数用于比较两个以 null 结尾的字符串，并返回一个整数值，根据它们的字典顺序关系来指示...
Meta Keywords: strcmp, str1, str2, const, char
-->

# strcmp 函数在 C 语言中的使用

## 概述
`strcmp` 是 C 语言中用于比较两个字符串的标准库函数。它的主要功能是确定两个字符串的字典顺序关系。

## 文档
### 目的
`strcmp` 函数用于比较两个以 null 结尾的字符串，并返回一个整数值，根据它们的字典顺序关系来指示它们的相对大小。

### 使用
函数原型：
```c
int strcmp(const char *str1, const char *str2);
```

#### 参数
- `str1`：指向第一个字符串的指针。
- `str2`：指向第二个字符串的指针。

#### 返回值
- 如果 `str1` 小于 `str2`，则返回一个负值。
- 如果 `str1` 等于 `str2`，则返回 0。
- 如果 `str1` 大于 `str2`，则返回一个正值。

### 详细说明
`strcmp` 函数逐字符比较两个字符串，直到找到不同的字符或到达字符串的结束。如果在比较过程中，某个字符串已经结束而另一个字符串还未结束，则较短的字符串被认为小于较长的字符串。该函数在 `<string.h>` 头文件中定义。

## 示例
以下是 `strcmp` 函数的基本用法示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "abc";
    const char *str2 = "abc";
    const char *str3 = "abcd";
    const char *str4 = "abC";

    printf("strcmp(str1, str2): %d\n", strcmp(str1, str2)); // 输出 0
    printf("strcmp(str1, str3): %d\n", strcmp(str1, str3)); // 输出负值
    printf("strcmp(str1, str4): %d\n", strcmp(str1, str4)); // 输出正值
    return 0;
}
```

## 解释
使用 `strcmp` 函数时需要注意以下几点：
- 字符串比较是区分大小写的，即 `strcmp("abc", "ABC")` 将返回正值。
- 函数的返回值是基于字符的 ASCII 值，因此相同字符的比较可能导致负数或正数的返回。
- 确保传递给 `strcmp` 的字符串都是以 null 结尾的字符串，如果不是，可能会导致未定义行为。
- `strcmp` 不会检查 NULL 指针，因此在调用之前应确保字符串指针有效。

## 一句话总结
`strcmp` 是一个用于比较两个字符串并返回其字典顺序关系的 C 语言标准库函数。