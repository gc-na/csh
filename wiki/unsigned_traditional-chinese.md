<!--
Meta Description: # C 語言中的 unsigned: 無符號整數的詳細介紹 ## 摘要 在 C 語言中，`unsigned` 關鍵字用於定義無符號整數類型，這類型不包括負數，從而擴大了可表示的正整數範圍。 ## 文檔 ### 目的 `unsigned` 是 C 語言中的一個關鍵字，用來指示變量的數據類型為無符號整數...
Meta Keywords: unsigned, int, long, sum, result
-->

# C 語言中的 unsigned: 無符號整數的詳細介紹

## 摘要
在 C 語言中，`unsigned` 關鍵字用於定義無符號整數類型，這類型不包括負數，從而擴大了可表示的正整數範圍。

## 文檔
### 目的
`unsigned` 是 C 語言中的一個關鍵字，用來指示變量的數據類型為無符號整數。這意味著該變量只能表示非負整數，這在需要處理大範圍的正整數時非常有用。

### 使用方式
在 C 語言中，可以將 `unsigned` 用於以下數據類型：
- `unsigned int`
- `unsigned short`
- `unsigned long`
- `unsigned long long`

這些類型的主要區別在於它們所能表示的數字範圍，無符號整數的範圍通常是從 0 到 2 的 n 次方減 1，其中 n 是位數。

例如：
```c
unsigned int num;  // 定義一個無符號整數
```

### 詳細資訊
使用 `unsigned` 時，要注意以下幾點：
- 無符號整數的範圍是從 0 開始，這使它們在處理需要避免負數的場合中非常有效。
- `unsigned` 整數類型的大小通常取決於系統架構，通常為 16 位、32 位或 64 位。
- `unsigned` 可以與其他數據類型結合使用，例如 `unsigned char` 和 `unsigned long`。

## 範例
以下是使用 `unsigned` 的基本範例：

```c
#include <stdio.h>

int main() {
    unsigned int a = 5;
    unsigned int b = 10;
    unsigned int sum = a + b;

    printf("Sum of %u and %u is %u\n", a, b, sum);
    return 0;
}
```
輸出：
```
Sum of 5 and 10 is 15
```

### 進階範例
使用 `unsigned` 進行位運算：
```c
#include <stdio.h>

int main() {
    unsigned int x = 0b00001111; // 二進制
    unsigned int y = 0b11110000;

    unsigned int result = x & y; // 位與運算

    printf("Result of AND operation: %u\n", result);
    return 0;
}
```
輸出：
```
Result of AND operation: 0
```

## 解釋
在使用 `unsigned` 類型時，有幾個常見的陷阱：
- **溢出問題**：如果對無符號整數進行減法運算時，結果小於 0，則會產生溢出，結果將循環到無符號整數的最大值。
- **類型轉換**：在進行運算時，`unsigned` 可能會與其他類型（如有符號整數）混合，導致意外的行為。
- **比較操作**：在比較有符號和無符號整數時，可能會導致意外的結果，因為 C 語言會自動將有符號整數轉換為無符號整數。

## 一句總結
在 C 語言中，`unsigned` 用於定義無符號整數，能夠有效地表示更大的正整數範圍。