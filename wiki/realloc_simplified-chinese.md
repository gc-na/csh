<!--
Meta Description: # C语言中的realloc函数详解 ## 概述 `realloc`是C标准库中的一个内存管理函数，用于调整已分配内存块的大小。它可以扩展或缩小已分配内存区的大小，并返回指向新内存块的指针。 ## 文档 ### 目的 `realloc`函数用于重新分配内存，允许程序动态调整内存的使用，尤其在处理数据...
Meta Keywords: realloc, arr, int, null, new_size
-->

# C语言中的realloc函数详解

## 概述
`realloc`是C标准库中的一个内存管理函数，用于调整已分配内存块的大小。它可以扩展或缩小已分配内存区的大小，并返回指向新内存块的指针。

## 文档
### 目的
`realloc`函数用于重新分配内存，允许程序动态调整内存的使用，尤其在处理数据结构如数组时非常有用。

### 用法
`realloc`函数的原型定义在`<stdlib.h>`头文件中：

```c
void* realloc(void* ptr, size_t new_size);
```

- **参数**：
  - `ptr`：指向之前已分配内存的指针，如果`ptr`为`NULL`，`realloc`的行为等同于`malloc(new_size)`。
  - `new_size`：所需的新内存大小（以字节为单位）。
  
- **返回值**：
  - 成功时，返回指向新内存块的指针。
  - 如果分配失败，返回`NULL`，且原内存块保持不变。

### 细节
- 当`new_size`为0时，`realloc`会释放内存并返回`NULL`。
- 如果`realloc`成功分配新的内存，它会将原内存块的数据复制到新内存块中。
- 调用`realloc`后，原内存块可能会被释放，因此原来的指针不再有效。
- 使用`realloc`时，务必注意处理返回值，以避免内存泄漏或未定义行为。

## 示例
### 基本用法
以下示例演示了如何使用`realloc`来调整数组的大小：

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int* arr = malloc(5 * sizeof(int)); // 分配5个整数的内存
    for (int i = 0; i < 5; i++) {
        arr[i] = i + 1; // 初始化数组
    }

    // 调整数组大小
    arr = realloc(arr, 10 * sizeof(int)); // 扩展为10个整数的内存
    if (arr == NULL) {
        fprintf(stderr, "内存重新分配失败\n");
        return 1;
    }

    // 初始化新分配的内存
    for (int i = 5; i < 10; i++) {
        arr[i] = i + 1; // 初始化新部分
    }

    // 打印数组内容
    for (int i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }
    
    free(arr); // 释放内存
    return 0;
}
```

## 解释
- **常见陷阱**：在调用`realloc`后，旧指针若未被赋值为`NULL`，将指向不再有效的内存，可能导致未定义行为。
- **内存泄漏**：在检查`realloc`返回值时，必须立即处理。如果不处理`NULL`返回值，可能会导致内存泄漏，尤其在多次调用时。
- **注意事项**：确保在使用`realloc`后更新原指针，避免使用已失效的指针。

## 一句话总结
`realloc`函数用于动态调整已分配内存块的大小，提供灵活的内存管理能力。