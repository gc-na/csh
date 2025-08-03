<!--
Meta Description: # C 語言中的 strchr 函數：字元搜尋工具 ## 簡介 `strchr` 是 C 語言中的一個標準函數，主要用於在字串中搜尋特定字元。此函數對於處理字串時的字元定位非常有用，特別是在解析文本數據時。 ## 文檔 ### 目的 `strchr` 函數的主要目的是在給定的字串中搜尋第一個出現的指...
Meta Keywords: strchr, null, result, str, char
-->

# C 語言中的 strchr 函數：字元搜尋工具

## 簡介
`strchr` 是 C 語言中的一個標準函數，主要用於在字串中搜尋特定字元。此函數對於處理字串時的字元定位非常有用，特別是在解析文本數據時。

## 文檔
### 目的
`strchr` 函數的主要目的是在給定的字串中搜尋第一個出現的指定字元，並返回該字元在字串中的指標。如果字元不存在，則返回 NULL。

### 語法
```c
char *strchr(const char *str, int c);
```

### 參數
- `str`：指向要搜尋的字串的指標。
- `c`：要搜尋的字元（以整數形式傳遞）。

### 返回值
- 如果找到指定字元，返回指向該字元的指標。
- 如果未找到，返回 NULL。

### 使用範例
以下是一些 `strchr` 函數的基本用法示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *result;

    // 尋找字元 'W'
    result = strchr(str, 'W');
    if (result != NULL) {
        printf("找到字元: %s\n", result); // 顯示 "World!"
    } else {
        printf("字元未找到。\n");
    }

    // 尋找字元 'x'
    result = strchr(str, 'x');
    if (result != NULL) {
        printf("找到字元: %s\n", result);
    } else {
        printf("字元未找到。\n"); // 這裡會顯示 "字元未找到。"
    }

    return 0;
}
```

## 解釋
在使用 `strchr` 時，有幾個常見的注意事項：

1. **字元範圍**：`c` 參數是以整數形式傳遞的字元，需確保使用正確的 ASCII 值或字符。
2. **結果處理**：返回的指標可能是 NULL，因此在解引用之前務必檢查是否為 NULL，以避免程式崩潰。
3. **字串結尾**：`strchr` 可以找到字串中的空字符（`'\0'`），這會返回指向字串結尾的指標。

## 一行總結
`strchr` 函數用於在字串中搜尋第一個指定字元，並返回其指標或 NULL。