<!--
Meta Description: # C 語言中的「signed」：數據類型與符號擴展 ## 摘要 在 C 語言中，「signed」是一個關鍵字，用於定義帶符號的整數數據類型，允許變量存儲正數和負數。這個關鍵字對於正確處理數據的範圍至關重要。 ## 文檔 ### 目的 「signed」關鍵字主要用於明確指定整數類型的符號性質。在 C...
Meta Keywords: signed, int, char, sum, result
-->

# C 語言中的「signed」：數據類型與符號擴展

## 摘要
在 C 語言中，「signed」是一個關鍵字，用於定義帶符號的整數數據類型，允許變量存儲正數和負數。這個關鍵字對於正確處理數據的範圍至關重要。

## 文檔
### 目的
「signed」關鍵字主要用於明確指定整數類型的符號性質。在 C 中，整數類型默認是「signed」，但當需要明確表達時，仍然可以使用此關鍵字。

### 使用
在 C 語言中，可以將「signed」與各種整數數據類型結合使用，如 `signed int`、`signed char`、`signed short` 和 `signed long`。這些類型可以存儲從負數到正數的數據。

#### 語法範例
```c
signed int a;      // 帶符號整數
signed char b;     // 帶符號字符
```

這些定義的變量可以用於數學運算，且能夠處理負值。

### 詳細說明
- **默認情況**：在 C 語言中，整數類型（如 `int` 和 `char`）如果不明確指定，則默認為「signed」。
- **範圍**：`signed int` 的範圍通常為 -2,147,483,648 到 2,147,483,647（32 位系統）。
- **符號擴展**：在進行運算時，帶符號數據類型會進行符號擴展，確保負數能正確表達。

## 示例
以下是一些使用「signed」的基本例子：

```c
#include <stdio.h>

int main() {
    signed int a = -10;
    signed int b = 20;
    signed int sum = a + b;

    printf("Sum: %d\n", sum); // 輸出：Sum: 10
    return 0;
}
```

```c
#include <stdio.h>

int main() {
    signed char c = -5;
    signed char d = 10;
    signed char result = c + d;

    printf("Result: %d\n", result); // 輸出：Result: 5
    return 0;
}
```

## 解釋
### 常見陷阱與注意事項
1. **範圍限制**：使用「signed」類型時，需要注意其範圍限制，以避免溢出。
2. **與無符號類型混合**：在與無符號類型（如 `unsigned int`）進行運算時，可能會導致意外的行為，因為無符號整數不會接受負值。
3. **明確性**：雖然整數類型默認為「signed」，在某些情況下，為了提高代碼的可讀性，明確使用「signed」可能是有益的。

## 總結
「signed」關鍵字在 C 語言中用於定義帶符號的整數類型，允許變量存儲負數和正數，並在數據處理中提供正確的符號表示。