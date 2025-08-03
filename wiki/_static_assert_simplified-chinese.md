<!--
Meta Description: # _Static_assert：C语言中的静态断言 ## 摘要 _static_assert 是 C11 标准引入的一种编译时断言机制，用于在编译时验证条件的正确性。这对于确保代码的安全性和正确性非常重要。 ## 文档 ### 目的 _static_assert 的主要目的是提供一种方法，以便在编...
Meta Keywords: _static_assert, c11, int, size, bytes
-->

# _Static_assert：C语言中的静态断言

## 摘要
_static_assert 是 C11 标准引入的一种编译时断言机制，用于在编译时验证条件的正确性。这对于确保代码的安全性和正确性非常重要。

## 文档
### 目的
_static_assert 的主要目的是提供一种方法，以便在编译期间检查某些条件是否为真。如果条件为假，编译器将抛出错误，从而防止不符合条件的代码编译通过。这在类型安全和接口契约方面非常有用。

### 用法
_static_assert 的语法如下：
```c
_Static_assert(expression, message);
```
- **expression**：一个整型表达式，必须在编译时能够被求值。
- **message**：一个字符串字面量，表示错误消息，当表达式求值为假时，该消息将被输出。

### 细节
- _static_assert 是 C11 标准的一部分，确保在编译期间进行错误检查。
- 该特性不依赖于运行时，因此可以在头文件中安全使用。
- _static_assert 只允许在全局作用域或函数内部使用。

## 示例
```c
#include <stdio.h>

_Static_assert(sizeof(int) == 4, "int size is not 4 bytes");

int main() {
    printf("Size of int is 4 bytes as expected.\n");
    return 0;
}
```
在此示例中，如果 `sizeof(int)` 不是 4 字节，编译器将会抛出错误，并显示 "int size is not 4 bytes"。

## 解释
### 常见问题
- **编译器支持**：_static_assert 是 C11 标准的一部分，因此只有支持 C11 的编译器才能使用此特性。确保你的编译器（如 GCC、Clang 或 MSVC）版本支持 C11。
- **消息限制**：错误消息必须是字符串字面量，不能使用变量或计算结果。

### 注意事项
- _static_assert 不能在条件中使用非整数类型，例如浮点数或指针。
- 不能在 _static_assert 中使用动态计算的值，因为它需要在编译时求值。

## 一句话总结
_static_assert 是 C11 提供的一种编译时断言机制，用于确保特定条件在编译时为真，以增强代码的安全性和可靠性。