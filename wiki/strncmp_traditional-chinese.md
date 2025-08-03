<!--
Meta Description: # C 語言中的 `strncmp` 函數詳解 ## 概述 `strncmp` 是 C 語言中用於比較兩個字串的函數，其功能是比較字串的前幾個字符，以確定它們是否相同。該函數通常用於需要比較固定長度的字串時，特別是在處理用戶輸入或檔案內容時。 ## 文檔 ### 目的 `strncmp` 函數的主要...
Meta Keywords: strncmp, str1, str2, 個字符, const
-->

# C 語言中的 `strncmp` 函數詳解

## 概述
`strncmp` 是 C 語言中用於比較兩個字串的函數，其功能是比較字串的前幾個字符，以確定它們是否相同。該函數通常用於需要比較固定長度的字串時，特別是在處理用戶輸入或檔案內容時。

## 文檔
### 目的
`strncmp` 函數的主要目的是在不完全比較整個字串的情況下，檢查兩個字串在指定長度內的相等性。

### 使用方法
```c
#include <string.h>

int strncmp(const char *str1, const char *str2, size_t n);
```

### 參數
- `str1`：指向要比較的第一個字串的指標。
- `str2`：指向要比較的第二個字串的指標。
- `n`：要比較的字符數量。

### 返回值
- 如果 `str1` 和 `str2` 的前 `n` 個字符相同，則返回 0。
- 如果 `str1` 的前 `n` 個字符大於 `str2` 的前 `n` 個字符，則返回正值。
- 如果 `str1` 的前 `n` 個字符小於 `str2` 的前 `n` 個字符，則返回負值。

## 範例
以下是 `strncmp` 函數的基本用法示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hello World";
    const char *str2 = "Hello Universe";

    int result = strncmp(str1, str2, 5); // 比較前 5 個字符
    if (result == 0) {
        printf("前 5 個字符相同\n");
    } else {
        printf("前 5 個字符不同\n");
    }

    return 0;
}
```

在此例中，`strncmp` 將比較 `str1` 和 `str2` 的前 5 個字符，因為它們相同，因此輸出為 "前 5 個字符相同"。

## 說明
- **注意字符長度**：使用 `strncmp` 時，請務必注意指定的長度不應超過任一字串的實際長度，否則可能導致不必要的比較。
- **終止字符**：如果在比較的字符中遇到終止字符（`'\0'`），則 `strncmp` 將停止比較。這意味著即使指定的長度較大，但如果字串長度小於指定的長度，仍然可以正確地進行比較。
- **性能考量**：`strncmp` 在比較時僅檢查前 `n` 個字符，因此在處理大字串時，相比於使用 `strcmp`，可以提高性能。

## 總結
`strncmp` 是一個在 C 語言中用於部分字串比較的實用函數，適合用於需要限制比較長度的情境。