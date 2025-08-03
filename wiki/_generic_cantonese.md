<!--
Meta Description: # C 語言中的 _Generic：一個簡單的類型選擇機制 ## 簡介 `_Generic` 是 C 語言中的一個關鍵字，用於實現基於類型的選擇。它允許根據給定表達式的類型選擇相應的行為，這樣可以在編譯期間進行類型安全的操作。 ## 文檔 ### 目的 `_Generic` 主要用於簡化函數的重載，...
Meta Keywords: _generic, type_of, printf, default, expression
-->

# C 語言中的 _Generic：一個簡單的類型選擇機制

## 簡介
`_Generic` 是 C 語言中的一個關鍵字，用於實現基於類型的選擇。它允許根據給定表達式的類型選擇相應的行為，這樣可以在編譯期間進行類型安全的操作。

## 文檔
### 目的
`_Generic` 主要用於簡化函數的重載，通過根據不同的數據類型選擇不同的表達式來提高代碼的可讀性和可維護性。

### 使用
`_Generic` 的基本語法如下：
```c
_Generic(expression, type1: expression1, type2: expression2, ..., default: default_expression)
```
- `expression` 是要檢查類型的表達式。
- `type1`, `type2`, ... 是可能的類型。
- `expression1`, `expression2`, ... 是對應於類型的表達式。
- `default_expression` 是在沒有匹配的類型時執行的默認表達式。

### 詳細說明
使用 `_Generic` 時，編譯器會根據表達式的類型選擇相應的表達式。這樣可以避免使用大量的 `if` 語句或類似的結構來實現類型檢查。

## 範例
以下是使用 `_Generic` 的基本示例：

```c
#include <stdio.h>

#define type_of(x) _Generic((x), \
    int: "整數", \
    float: "浮點數", \
    double: "雙精度浮點數", \
    default: "未知類型")

int main() {
    printf("type_of(5): %s\n", type_of(5));        // 輸出：整數
    printf("type_of(5.0f): %s\n", type_of(5.0f));  // 輸出：浮點數
    printf("type_of(5.0): %s\n", type_of(5.0));    // 輸出：雙精度浮點數
    printf("type_of(\"hello\"): %s\n", type_of("hello")); // 輸出：未知類型
    return 0;
}
```

## 解釋
使用 `_Generic` 時需注意以下幾點：
- `_Generic` 只能在表達式中使用，無法單獨用作語句。
- 若提供的類型與表達式類型不匹配，則將選擇 `default` 表達式（如果有提供）。
- `_Generic` 不能用來對類型進行運算或比較，只能用於選擇表達式。

## 一句總結
`_Generic` 是 C 語言的一個強大工具，用於在編譯期間根據表達式的類型選擇相應的行為。