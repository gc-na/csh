<!--
Meta Description: # C 語言中的 strlen 函數：計算字串長度的利器 ## 簡介 在 C 語言中，`strlen` 函數是一個標準庫函數，用於計算以 null 字元結束的字串的長度。這個函數對於字串處理至關重要，因為它幫助開發者確定字串的實際大小。 ## 文檔 ### 目的 `strlen` 函數的主要目的在於...
Meta Keywords: strlen, null, str, include, size_t
-->

# C 語言中的 strlen 函數：計算字串長度的利器

## 簡介
在 C 語言中，`strlen` 函數是一個標準庫函數，用於計算以 null 字元結束的字串的長度。這個函數對於字串處理至關重要，因為它幫助開發者確定字串的實際大小。

## 文檔
### 目的
`strlen` 函數的主要目的在於返回字串中字符的數量，並不包括結尾的 null 字元 (`\0`)。這對於處理字串和確定緩衝區大小非常有用。

### 語法
```c
#include <string.h>

size_t strlen(const char *str);
```

### 參數
- `str`: 指向以 null 字元結束的字串的指針。

### 返回值
`strlen` 返回字串的長度，類型為 `size_t`，如果指針為 `NULL`，則行為未定義。

### 使用
在使用 `strlen` 時，確保傳入的字串是有效且已正確終止的，否則可能導致未定義行為。

## 範例
以下是使用 `strlen` 的基本範例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    size_t length = strlen(str);
    printf("字串長度: %zu\n", length);
    return 0;
}
```

輸出：
```
字串長度: 13
```

## 解釋
在使用 `strlen` 時，需注意以下幾點：
- **null 結尾**: `strlen` 僅計算到第一個 null 字元為止，因此傳入的字串必須以 `\0` 結尾。
- **未定義行為**: 如果傳遞給 `strlen` 的指針是 `NULL`，將導致程式崩潰或未定義行為。
- **性能注意**: `strlen` 將遍歷整個字串以計算長度，對於非常長的字串，這可能會影響效能。

## 一句總結
`strlen` 函數是 C 語言中用於計算字串長度的基本工具，簡單而高效。