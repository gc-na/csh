<!--
Meta Description: # strcmp 函數在 C 語言中的應用與使用指南 ## 摘要 `strcmp` 是 C 語言中的一個標準函數，用於比較兩個字串，並根據字串的字典順序返回結果。這個函數廣泛應用於字串處理和排序算法中。 ## 文檔 ### 目的 `strcmp` 函數主要用於比較兩個以空字符結束的字串。它在字符串的...
Meta Keywords: strcmp, str1, str2, int, const
-->

# strcmp 函數在 C 語言中的應用與使用指南

## 摘要
`strcmp` 是 C 語言中的一個標準函數，用於比較兩個字串，並根據字串的字典順序返回結果。這個函數廣泛應用於字串處理和排序算法中。

## 文檔
### 目的
`strcmp` 函數主要用於比較兩個以空字符結束的字串。它在字符串的字典序排列中起到了關鍵作用，通常用於排序或判斷字串的相等性。

### 使用方法
在使用 `strcmp` 函數時，需包含 `string.h` 標頭檔案。函數的基本語法如下：

```c
int strcmp(const char *str1, const char *str2);
```

#### 參數
- `str1`：第一個要比較的字串。
- `str2`：第二個要比較的字串。

#### 返回值
- 若 `str1` 等於 `str2`，則返回 0。
- 若 `str1` 小於 `str2`，則返回一個小於 0 的值。
- 若 `str1` 大於 `str2`，則返回一個大於 0 的值。

## 示例
以下是 `strcmp` 的基本使用範例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "apple";
    const char *str2 = "banana";
    const char *str3 = "apple";

    int result1 = strcmp(str1, str2); // 返回小於 0
    int result2 = strcmp(str1, str3); // 返回 0
    int result3 = strcmp(str2, str1); // 返回大於 0

    printf("result1: %d\n", result1); // 輸出結果
    printf("result2: %d\n", result2); // 輸出結果
    printf("result3: %d\n", result3); // 輸出結果

    return 0;
}
```

## 解釋
在使用 `strcmp` 時，有幾個常見的陷阱和注意事項：
- **大小寫敏感**：`strcmp` 是大小寫敏感的，"apple" 和 "Apple" 會被視為不同的字串。
- **空字串**：比較一個空字串與非空字串時，空字串總是被視為小於任何非空字串。
- **未定義行為**：如果傳入的指標指向非字串或未初始化的記憶體，則會導致未定義行為，必須確保傳入的參數是有效的 C 字串。

## 一句總結
`strcmp` 是一個用於比較兩個字串的 C 標準函數，通過返回整數值來指示字串的相對大小或相等性。