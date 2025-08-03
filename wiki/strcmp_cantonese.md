<!--
Meta Description: # strcmp 函數：C 語言中的字串比較工具 ## 概要 `strcmp` 是 C 語言中用於比較兩個字串的標準函數。它能夠判斷兩個字串的字典順序以及是否相等，廣泛應用於字串處理和排序等場景。 ## 文件說明 `strcmp` 函數的原型定義在 `<string.h>` 標頭檔中，其基本用途是比...
Meta Keywords: strcmp, str1, str2, int, const
-->

# strcmp 函數：C 語言中的字串比較工具

## 概要
`strcmp` 是 C 語言中用於比較兩個字串的標準函數。它能夠判斷兩個字串的字典順序以及是否相等，廣泛應用於字串處理和排序等場景。

## 文件說明
`strcmp` 函數的原型定義在 `<string.h>` 標頭檔中，其基本用途是比較兩個以 null 結尾的字串。這個函數的語法如下：

```c
int strcmp(const char *str1, const char *str2);
```

### 用途
- **比較字串**：用於判斷兩個字串是否相等或其字典排序位置。
- **排序功能**：在字串排序演算法中，常用於決定字串的順序。

### 參數
- `str1`：第一個要比較的字串。
- `str2`：第二個要比較的字串。

### 返回值
- 返回一個整數：
  - 如果 `str1` 和 `str2` 相等，返回 `0`。
  - 如果 `str1` 小於 `str2`，返回負數。
  - 如果 `str1` 大於 `str2`，返回正數。

## 範例
以下是 `strcmp` 的基本使用範例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "apple";
    const char *str2 = "banana";
    const char *str3 = "apple";

    int result1 = strcmp(str1, str2); // 返回負數
    int result2 = strcmp(str1, str3); // 返回 0
    int result3 = strcmp(str2, str1); // 返回正數

    printf("Comparing '%s' and '%s': %d\n", str1, str2, result1);
    printf("Comparing '%s' and '%s': %d\n", str1, str3, result2);
    printf("Comparing '%s' and '%s': %d\n", str2, str1, result3);

    return 0;
}
```

## 解釋
- **常見陷阱**：使用 `strcmp` 時，需確保兩個字串均為以 null 結尾的字串。若未正確以 null 結尾，可能導致未定義行為或程式崩潰。
- **字母大小寫**：`strcmp` 是區分大小寫的，"apple" 和 "Apple" 會被視為不同的字串。
- **字串長度**：在比較長度不相同的字串時，`strcmp` 會根據 ASCII 值逐字比較，直至遇到不同字符或到達結尾。

## 一句總結
`strcmp` 是 C 語言中用於比較字串的標準函數，返回字串之間的相對順序或相等性。