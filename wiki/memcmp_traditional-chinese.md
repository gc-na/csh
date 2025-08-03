<!--
Meta Description: # C 語言中的 `memcmp` 函式：比較記憶體區域的有效工具 ## 摘要 `memcmp` 是 C 語言標準庫中一個重要的函式，用於比較兩個記憶體區域的內容是否相同，並返回比較結果。該函式廣泛應用於處理字串和二進位數據。 ## 文檔 ### 目的 `memcmp` 函式的主要目的是比較兩個記憶...
Meta Keywords: memcmp, str1, ptr1, ptr2, int
-->

# C 語言中的 `memcmp` 函式：比較記憶體區域的有效工具

## 摘要
`memcmp` 是 C 語言標準庫中一個重要的函式，用於比較兩個記憶體區域的內容是否相同，並返回比較結果。該函式廣泛應用於處理字串和二進位數據。

## 文檔
### 目的
`memcmp` 函式的主要目的是比較兩個記憶體區域，通常用於檢查數據是否相等或判斷其大小關係。

### 使用方式
`memcmp` 函式的原型定義如下：
```c
int memcmp(const void *ptr1, const void *ptr2, size_t num);
```
#### 參數
- `ptr1`：指向第一個記憶體區域的指標。
- `ptr2`：指向第二個記憶體區域的指標。
- `num`：要比較的字節數。

#### 返回值
- 當 `ptr1` 所指向的記憶體區域與 `ptr2` 所指向的記憶體區域相等，返回 0。
- 若 `ptr1` 所指向的記憶體區域小於 `ptr2`，返回一個小於 0 的負值。
- 若 `ptr1` 所指向的記憶體區域大於 `ptr2`，返回一個大於 0 的正值。

## 範例
以下是 `memcmp` 函式的基本使用範例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "Hello";
    char str3[] = "World";

    // 比較 str1 和 str2
    int result1 = memcmp(str1, str2, sizeof(str1));
    // 比較 str1 和 str3
    int result2 = memcmp(str1, str3, sizeof(str1));

    printf("比較 str1 與 str2 的結果：%d\n", result1); // 輸出：0
    printf("比較 str1 與 str3 的結果：%d\n", result2); // 輸出：小於 0
    return 0;
}
```

## 解釋
- **常見陷阱**：使用 `memcmp` 時，需確保比較的字節數 (`num`) 不超過兩個記憶體區域的實際大小，否則可能導致未定義行為。
- **資料類型**：`memcmp` 是以位元組為單位進行比較，對於不同資料類型的比較需小心，特別是浮點數和結構體。
- **字串結束符**：在比較字串時，需確保包含結束符 (`\0`)，以避免比較不必要的記憶體空間。

## 單行摘要
`memcmp` 是 C 語言中的一個函式，用於有效比較兩個記憶體區域的內容，返回比較結果。