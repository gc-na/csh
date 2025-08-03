<!--
Meta Description: # C 語言中的 isgraph 函數：檢查可顯示字符 ## 概述 `isgraph` 函數是 C 語言中的一個標準庫函數，用於檢查一個字符是否為可顯示字符（不包括空格）。這個函數對於處理文本數據和字符驗證非常有用。 ## 文檔 ### 目的 `isgraph` 函數的主要目的是判斷給定的字符是否是...
Meta Keywords: isgraph, 是可顯示字符, printf, char, 不是可顯示字符
-->

# C 語言中的 isgraph 函數：檢查可顯示字符

## 概述
`isgraph` 函數是 C 語言中的一個標準庫函數，用於檢查一個字符是否為可顯示字符（不包括空格）。這個函數對於處理文本數據和字符驗證非常有用。

## 文檔
### 目的
`isgraph` 函數的主要目的是判斷給定的字符是否是可顯示字符，這些字符包括字母、數字和其他符號，但不包括空格字符。

### 使用方法
`isgraph` 函數的原型如下：

```c
#include <ctype.h>

int isgraph(int c);
```

- **參數**：`c` 是需要檢查的字符，通常以整數類型傳遞，這通常是通過轉換字符來獲得。
- **返回值**：如果字符 `c` 是可顯示字符，則返回非零值；否則返回 0。

### 詳細說明
`isgraph` 函數是 C 標準庫的一部分，包含在 `<ctype.h>` 頭文件中。它的主要功能是檢查字符是否在可顯示字符的範疇內。可顯示字符的範圍包括 ASCII 中的字符 `33` 到 `126`（即從 `'!'` 到 `'~'`），不包括空格字符 `32`。

## 示例
以下是使用 `isgraph` 函數的基本範例：

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char testChar1 = 'A';
    char testChar2 = ' ';
    char testChar3 = '1';
    char testChar4 = '#';

    if (isgraph(testChar1)) {
        printf("%c 是可顯示字符。\n", testChar1);
    } else {
        printf("%c 不是可顯示字符。\n", testChar1);
    }

    if (isgraph(testChar2)) {
        printf("%c 是可顯示字符。\n", testChar2);
    } else {
        printf("%c 不是可顯示字符。\n", testChar2);
    }

    if (isgraph(testChar3)) {
        printf("%c 是可顯示字符。\n", testChar3);
    } else {
        printf("%c 不是可顯示字符。\n", testChar3);
    }

    if (isgraph(testChar4)) {
        printf("%c 是可顯示字符。\n", testChar4);
    } else {
        printf("%c 不是可顯示字符。\n", testChar4);
    }

    return 0;
}
```

### 輸出：
```
A 是可顯示字符。
  不是可顯示字符。
1 是可顯示字符。
# 是可顯示字符。
```

## 解釋
在使用 `isgraph` 函數時，需注意以下幾點：
- **字符範圍**：`isgraph` 僅適用於 `unsigned char` 範圍內的字符（0 到 255）。對於負值或大於 255 的整數，行為未定義。
- **可移植性**：在不同的編譯器或平台上，字符集的實現可能會有所不同，但 ANSI C 標準規定了 `isgraph` 的行為，確保其在大多數環境中的一致性。
- **與其他函數的區別**：`isprint` 函數檢查字符是否可顯示，包括空格，而 `isgraph` 僅檢查非空格可顯示字符。

## 總結
`isgraph` 函數是一個用於檢查字符是否為可顯示字符的實用工具，對於字符數據的驗證和處理至關重要。