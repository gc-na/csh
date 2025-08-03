<!--
Meta Description: # C语言中的floor函数：用法和示例 ## 概述 `floor` 函数是 C 语言中的一个数学库函数，用于返回小于或等于给定数字的最大整数。它通常用于需要进行数值舍入的场景。 ## 文档 ### 目的 `floor` 函数的主要目的是对浮点数进行向下取整，即将一个浮点数向下舍入到最近的整数值。 ...
Meta Keywords: floor, double, math, include, num1
-->

# C语言中的floor函数：用法和示例

## 概述
`floor` 函数是 C 语言中的一个数学库函数，用于返回小于或等于给定数字的最大整数。它通常用于需要进行数值舍入的场景。

## 文档
### 目的
`floor` 函数的主要目的是对浮点数进行向下取整，即将一个浮点数向下舍入到最近的整数值。

### 使用方法
`floor` 函数的原型定义在 `<math.h>` 头文件中，使用方法如下：

```c
#include <math.h>
double floor(double x);
```

#### 参数
- `x`：需要进行舍入的浮点数。

#### 返回值
- 返回值为小于或等于 `x` 的最大整数，类型为 `double`。如果 `x` 为 NaN（非数值），则返回 NaN；如果 `x` 为正无穷大或负无穷大，则返回相应的无穷大。

### 示例
以下是一些使用 `floor` 函数的基本示例：

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num1 = 3.7;
    double num2 = -2.3;
    
    printf("floor(%.1f) = %.1f\n", num1, floor(num1));  // 输出: 3.0
    printf("floor(%.1f) = %.1f\n", num2, floor(num2));  // 输出: -3.0

    return 0;
}
```

## 说明
使用 `floor` 函数时需要注意以下几点：
- `floor` 函数返回的是 `double` 类型，即使输入的是整数类型，返回值也会被提升为 `double`。
- 在使用时，应确保包含 `<math.h>` 头文件，否则编译时可能会出现未定义的引用错误。
- `floor` 函数的行为在负数时与正数不同：例如，`floor(-2.3)` 返回 `-3.0` 而不是 `-2.0`。

## 一句话总结
`floor` 函数用于获取小于或等于给定浮点数的最大整数值。