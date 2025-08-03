<!--
Meta Description: # C 語言中的 switch 語句：用法與示例 ## 概述 `switch` 語句是 C 語言中的一種控制結構，允許根據變數的值選擇執行不同的程式碼區塊，從而簡化多重條件判斷的過程。 ## 文檔 ### 目的 `switch` 語句提供了一種方便的方法來處理多個選擇情況，相比於多重的 `if-el...
Meta Keywords: case, switch, break, printf, expression
-->

# C 語言中的 switch 語句：用法與示例

## 概述
`switch` 語句是 C 語言中的一種控制結構，允許根據變數的值選擇執行不同的程式碼區塊，從而簡化多重條件判斷的過程。

## 文檔
### 目的
`switch` 語句提供了一種方便的方法來處理多個選擇情況，相比於多重的 `if-else` 語句，`switch` 更為簡潔和易讀。

### 用法
`switch` 語句的基本語法如下：

```c
switch (expression) {
    case constant1:
        // 程式碼區塊1
        break;
    case constant2:
        // 程式碼區塊2
        break;
    // 可選的更多情況
    default:
        // 預設程式碼區塊
}
```

- `expression` 是一個整數表達式，將與後續的常量進行比較。
- 每個 `case` 標籤後面跟隨一個常量，當 `expression` 的結果與這個常量匹配時，對應的程式碼區塊將會執行。
- `break` 語句用於終止 `switch` 語句，防止執行到下一個 `case`。
- `default` 是可選的，當所有 `case` 都不匹配時執行。

### 詳細說明
- `switch` 語句只能用於整數類型（如 `int`、`char`）的變數。
- 由於在 C 中 `case` 標籤必須是常量，因此無法用變數或表達式作為 `case` 的標籤。
- 多個 `case` 可以共用同一個程式碼區塊，只需不帶 `break`。

## 示例
以下是一個使用 `switch` 語句的簡單示例：

```c
#include <stdio.h>

int main() {
    int day = 3;
    switch (day) {
        case 1:
            printf("星期一\n");
            break;
        case 2:
            printf("星期二\n");
            break;
        case 3:
            printf("星期三\n");
            break;
        case 4:
            printf("星期四\n");
            break;
        case 5:
            printf("星期五\n");
            break;
        default:
            printf("無效的日期\n");
    }
    return 0;
}
```

在這個例子中，當 `day` 的值為3時，將輸出 "星期三"。

## 解釋
- **常見陷阱**：
  - 忘記加上 `break` 可能導致無意中執行了後續的 `case`，這被稱為「fall-through」。
  - 確保 `case` 的常量值是唯一的，否則會導致編譯錯誤。
  
- **其他注意事項**：
  - `switch` 語句的性能在某些情況下可能優於 `if-else`，特別是當 `case` 數量較多時。
  - `switch` 無法處理浮點數或字符串類型的比較。

## 一句總結
`switch` 是 C 語言中一種簡化多重條件判斷的控制結構，提供了清晰的選擇機制。