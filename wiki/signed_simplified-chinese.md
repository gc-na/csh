<!--
Meta Description: # C语言中的“signed”关键字详解 ## 概述 在C语言中，“signed”是一个类型修饰符，用于指定整数类型的符号性。它允许变量存储正值和负值。在C语言中，默认情况下，int类型是有符号的，但使用“signed”可以明确指定。 ## 文档 “signed”修饰符用于整数类型，主要包括： - ...
Meta Keywords: signed, int, char, short, long
-->

# C语言中的“signed”关键字详解

## 概述
在C语言中，“signed”是一个类型修饰符，用于指定整数类型的符号性。它允许变量存储正值和负值。在C语言中，默认情况下，int类型是有符号的，但使用“signed”可以明确指定。

## 文档
“signed”修饰符用于整数类型，主要包括：
- **signed int**: 它是一个有符号整数，能够表示正数、零和负数。
- **signed char**: 这是一个有符号字符类型，通常用于表示小的整数值。
- **signed short**: 这是一个有符号短整型，大多用于存储小范围的整数。
- **signed long**: 这是一个有符号长整型，能够存储更大的整数值。

### 用法
在C语言中，可以通过以下方式定义有符号的整数：
```c
signed int a = -10;
signed char b = 'A';
signed short c = -1000;
signed long d = -123456789L;
```
可以省略“signed”关键字，因为int, char, short 和 long 默认都是有符号的。例如，`int a = -10;`和`signed int a = -10;`是等效的。

## 示例
以下是一些示例代码，展示了“signed”的基本用法：

```c
#include <stdio.h>

int main() {
    signed int a = -10;
    signed char b = 'A';
    signed short c = -1000;
    signed long d = -123456789L;

    printf("a: %d\n", a);
    printf("b: %c\n", b);
    printf("c: %d\n", c);
    printf("d: %ld\n", d);

    return 0;
}
```

### 输出：
```
a: -10
b: A
c: -1000
d: -123456789
```

## 说明
使用“signed”时需要注意以下几点：
- 默认情况下，`int`, `char`, `short` 和 `long` 都是有符号的，因此在不指定“signed”时，它们仍然可以存储负值。
- 如果使用“unsigned”修饰符，则变量只能存储非负值。
- 在进行整数运算时，混合使用有符号和无符号类型可能会导致意想不到的结果，尤其是当有符号数参与到无符号数的运算中时。

### 常见陷阱
- 由于C语言的类型转换规则，混合使用有符号和无符号整数可能会导致负数被转换为非常大的正数。
- 在条件判断中，如果一个有符号整数被当做无符号数进行比较，可能会导致逻辑错误。

## 一句话总结
“signed”是C语言中的一个关键字，用于定义可表示负数和正数的整数类型。