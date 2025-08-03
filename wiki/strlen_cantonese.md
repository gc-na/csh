<!--
Meta Description: # C 語言中的 strlen 函數：計算字串長度的工具 ## 概要 `strlen` 是 C 語言中的一個標準庫函數，用於計算以 null 結尾的字串的長度。它是處理字串時常用的工具，幫助開發者了解字串中字符的數量。 ## 文檔 ### 目的 `strlen` 函數的主要目的是返回字串中字符的數量...
Meta Keywords: strlen, null, str, size_t, string
-->

# C 語言中的 strlen 函數：計算字串長度的工具

## 概要
`strlen` 是 C 語言中的一個標準庫函數，用於計算以 null 結尾的字串的長度。它是處理字串時常用的工具，幫助開發者了解字串中字符的數量。

## 文檔
### 目的
`strlen` 函數的主要目的是返回字串中字符的數量，不包括結尾的 null 字符（'\0'）。

### 用法
要使用 `strlen` 函數，首先需要包含標頭檔 `<string.h>`。其基本語法如下：

```c
size_t strlen(const char *str);
```

#### 參數
- `str`: 指向以 null 結尾的字串的指標。

#### 返回值
- 返回字串的長度（不包括 null 字符），類型為 `size_t`。

### 詳細說明
`strlen` 函數遍歷字串，直到遇到第一個 null 字符，並計算字符的數量。這個函數的時間複雜度為 O(n)，其中 n 是字串的長度。使用 `strlen` 時，需確保傳入的指標指向有效的字串。

## 範例
下面是一些使用 `strlen` 函數的基本範例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    size_t length = strlen(str);
    printf("字串長度: %zu\n", length); // 輸出: 字串長度: 13
    return 0;
}
```

在這個範例中，我們計算了字串 "Hello, World!" 的長度，並將結果輸出。

## 解釋
使用 `strlen` 時，開發者需要注意以下幾點：
- **空字串**: 如果傳入的字串為空（即 `""`），則 `strlen` 將返回 0。
- **未初始化指標**: 如果傳入的指標未初始化或指向無效內存，將導致未定義行為。使用前請確保指標有效。
- **多字節字符**: 對於多字節字符集（如 UTF-8），`strlen` 將計算字元數，而不是顯示的字符數，這在處理國際化字串時需特別注意。

## 一句總結
`strlen` 函數是 C 語言中用於計算以 null 結尾的字串長度的標準函數。