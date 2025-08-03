<!--
Meta Description: # fseek 函数在 C 语言中的使用 ## 概述 `fseek` 是 C 语言标准库中用于文件操作的一个函数，它允许程序在打开的文件中移动文件指针到指定的位置。此功能对于随机访问文件内容至关重要。 ## 文档 ### 目的 `fseek` 函数用于在文件流中设置文件指针的位置。它允许用户在文件中...
Meta Keywords: file, fseek, return, int, whence
-->

# fseek 函数在 C 语言中的使用

## 概述
`fseek` 是 C 语言标准库中用于文件操作的一个函数，它允许程序在打开的文件中移动文件指针到指定的位置。此功能对于随机访问文件内容至关重要。

## 文档
### 目的
`fseek` 函数用于在文件流中设置文件指针的位置。它允许用户在文件中任意位置读取或写入数据。

### 语法
```c
int fseek(FILE *stream, long offset, int whence);
```

### 参数
- `stream`：指向 `FILE` 类型的指针，表示要操作的文件流。
- `offset`：相对于 `whence` 的字节偏移量，可以是正值或负值。
- `whence`：指明偏移的起始位置，可以是以下常量之一：
  - `SEEK_SET`：从文件开头开始。
  - `SEEK_CUR`：从当前位置开始。
  - `SEEK_END`：从文件末尾开始。

### 返回值
- 成功时返回 0。
- 失败时返回 -1，并设置 errno 变量以指示错误类型。

## 示例
### 示例 1：将文件指针移动到文件开头
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("无法打开文件");
        return -1;
    }
    fseek(file, 0, SEEK_SET); // 移动到文件开头
    // ... 读取文件内容
    fclose(file);
    return 0;
}
```

### 示例 2：将文件指针移动到文件末尾
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("无法打开文件");
        return -1;
    }
    fseek(file, 0, SEEK_END); // 移动到文件末尾
    // ... 读取文件内容
    fclose(file);
    return 0;
}
```

### 示例 3：从当前位置向后移动 10 个字节
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("无法打开文件");
        return -1;
    }
    fseek(file, 10, SEEK_CUR); // 从当前位置向后移动 10 个字节
    // ... 读取文件内容
    fclose(file);
    return 0;
}
```

## 解释
- **常见错误**：使用 `fseek` 时，确保文件已正确打开，并且文件流处于可读或可写状态。文件指针的位置偏移不能超出文件的边界。
- **注意事项**：在使用 `fseek` 移动指针后，建议使用 `ftell` 函数获取当前指针位置，确保定位正确。对于文本文件，特别是在不同操作系统之间，换行符的处理可能会导致意外的行为。

## 一句话总结
`fseek` 是用于在 C 语言中文件流中定位文件指针的高效工具。