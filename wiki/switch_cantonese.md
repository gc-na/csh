<!--
Meta Description: # C 語言中的 switch 語句：用法與範例 ## 概述 `switch` 語句是 C 語言中的一個控制結構，用於根據變數的值選擇執行不同的程式碼塊。它是多重選擇的一種實現方式，能夠提高程式的可讀性和效率。 ## 文件說明 `switch` 語句的主要目的是簡化多條 `if-else` 判斷邏輯...
Meta Keywords: case, switch, break, default, printf
-->

# C 語言中的 switch 語句：用法與範例

## 概述
`switch` 語句是 C 語言中的一個控制結構，用於根據變數的值選擇執行不同的程式碼塊。它是多重選擇的一種實現方式，能夠提高程式的可讀性和效率。

## 文件說明
`switch` 語句的主要目的是簡化多條 `if-else` 判斷邏輯，當需要根據某個變數的特定值執行不同代碼時非常有用。其基本語法如下：

```c
switch (expression) {
    case constant1:
        // 執行的程式碼
        break;
    case constant2:
        // 執行的程式碼
        break;
    // 更多的 case
    default:
        // 當沒有任何 case 匹配時執行的程式碼
}
```

### 用法
- `expression` 是一個整數或字符類型的變數。
- `case` 是一個常數值，當 `expression` 的值與某個 `case` 的值匹配時，對應的程式碼將被執行。
- `break` 語句用於終止 `switch` 語句，防止執行後續的 `case`。
- `default` 是可選的，當沒有任何 `case` 匹配時執行的程式碼。

## 範例
以下是一個基本的 `switch` 語句的範例：

```c
#include <stdio.h>

int main() {
    int day = 3;

    switch (day) {
        case 1:
            printf("今天是星期一\n");
            break;
        case 2:
            printf("今天是星期二\n");
            break;
        case 3:
            printf("今天是星期三\n");
            break;
        default:
            printf("這不是一個有效的星期日\n");
    }

    return 0;
}
```

在此範例中，根據 `day` 的值，程式將輸出當前是星期幾。

## 解釋
- **常見陷阱**：
  - 忘記在每個 `case` 的結尾加上 `break`，這會導致執行進入下一個 `case`，形成意外的行為。
  - `switch` 只能用於整數類型或字符類型，不能用於浮點數或字符串。
  
- **額外說明**：
  - `case` 標籤必須是常數值，且不能重複。
  - `default` 標籤是可選的，但建議在需要處理未知情況時使用。

## 一句總結
`switch` 語句是 C 語言中用於根據變數的值選擇執行不同程式碼的一種高效控制結構。