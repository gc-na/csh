<!--
Meta Description: # C 語言中的 abs 函數：絕對值計算 ## 簡介 `abs` 函數是 C 語言標準庫中用於計算整數的絕對值的函數。它返回一個非負整數，代表輸入整數的絕對值。 ## 文檔 `abs` 函數的原型定義在 `<stdlib.h>` 標頭檔中。其用途是為了獲取給定整數的絕對值。這在數學運算中非常常見，...
Meta Keywords: abs, int, absolute, value, stdlib
-->

# C 語言中的 abs 函數：絕對值計算

## 簡介
`abs` 函數是 C 語言標準庫中用於計算整數的絕對值的函數。它返回一個非負整數，代表輸入整數的絕對值。

## 文檔
`abs` 函數的原型定義在 `<stdlib.h>` 標頭檔中。其用途是為了獲取給定整數的絕對值。這在數學運算中非常常見，特別是在需要比較數字大小或處理負數的情況下。

### 語法
```c
#include <stdlib.h>

int abs(int n);
```

### 參數
- `n`：要計算絕對值的整數。

### 返回值
- 返回 `n` 的絕對值。如果 `n` 為負數，則返回 `-n`；如果 `n` 為非負數，則返回 `n` 本身。

## 範例
以下是 `abs` 函數的基本使用範例：

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num1 = -10;
    int num2 = 5;
    
    printf("The absolute value of %d is %d\n", num1, abs(num1)); // 輸出: The absolute value of -10 is 10
    printf("The absolute value of %d is %d\n", num2, abs(num2)); // 輸出: The absolute value of 5 is 5
    
    return 0;
}
```

## 說明
使用 `abs` 函數時需要注意以下幾點：

1. **範圍限制**：`abs` 函數只能處理 `int` 類型的整數。如果需要計算其他數據類型（如 `long` 或 `float`）的絕對值，應使用相應的函數，如 `labs` 或 `fabs`。

2. **負零**：在 C 語言中，`-0` 和 `0` 是等價的，因此 `abs(0)` 和 `abs(-0)` 都會返回 `0`。

3. **性能考量**：`abs` 函數的計算非常快速，因為它僅涉及基本的條件判斷和可能的一次取負操作，適合在性能敏感的應用中使用。

## 一句總結
`abs` 函數是一個簡單而有效的工具，用於計算整數的絕對值。