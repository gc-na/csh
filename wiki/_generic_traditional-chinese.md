<!--
Meta Description: # C 語言中的 _Generic：泛型選擇運算子 ## 概要 `_Generic` 是 C 語言中的一個關鍵字，用於實現泛型編程，允許根據表達式的類型選擇不同的表達式。此功能在 C11 標準中引入，能夠簡化類型相關的邏輯處理。 ## 文檔 `_Generic` 是一種編譯時運算子，主要用於根據變數...
Meta Keywords: _generic, 的類型, type_name, expression, type1
-->

# C 語言中的 _Generic：泛型選擇運算子

## 概要
`_Generic` 是 C 語言中的一個關鍵字，用於實現泛型編程，允許根據表達式的類型選擇不同的表達式。此功能在 C11 標準中引入，能夠簡化類型相關的邏輯處理。

## 文檔
`_Generic` 是一種編譯時運算子，主要用於根據變數的類型選擇相應的操作或返回不同類型的值。這對於需要支持多種數據類型的函數或宏特別有用。

### 目的
`_Generic` 的主要目的是提供一種在編譯階段根據不同類型進行選擇的機制，從而避免使用大量的條件語句來處理不同數據類型。

### 用法
`_Generic` 的語法如下：
```c
_Generic(expression, type1: expression1, type2: expression2, ...)
```
- `expression` 是要檢查類型的表達式。
- `type1`, `type2` 是可能的類型。
- `expression1`, `expression2` 是對應於每種類型的表達式。

若 `expression` 的類型匹配 `type1`，則返回 `expression1` 的值；若匹配 `type2`，則返回 `expression2` 的值；以此類推。

## 範例
以下是 `_Generic` 的基本使用範例：

```c
#include <stdio.h>

#define TYPE_NAME(x) _Generic((x), \
    int: "整數", \
    float: "浮點數", \
    double: "雙精度浮點數", \
    default: "未知類型")

int main() {
    int a = 10;
    float b = 5.0;
    double c = 3.14;

    printf("a 的類型: %s\n", TYPE_NAME(a)); // 輸出: a 的類型: 整數
    printf("b 的類型: %s\n", TYPE_NAME(b)); // 輸出: b 的類型: 浮點數
    printf("c 的類型: %s\n", TYPE_NAME(c)); // 輸出: c 的類型: 雙精度浮點數

    return 0;
}
```

## 解釋
使用 `_Generic` 時需要注意以下幾點：
- `_Generic` 只能在表達式上下文中使用，不能單獨使用。
- 每個 `type` 必須是有效的 C 類型，例如基本類型、指標、結構等。
- 如果沒有匹配的類型，則會導致編譯錯誤，除非提供了 `default` 選項。
- `_Generic` 在選擇表達式時僅考慮表達式的靜態類型，而非其動態類型。

## 一句總結
`_Generic` 是 C 語言中的一個強大工具，允許根據變數的類型在編譯時選擇不同的表達式，以支持泛型編程。