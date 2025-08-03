<!--
Meta Description: # C 語言中的 case 陳述句：用於多重選擇的控制結構 ## 簡介 在 C 語言中，`case` 陳述句是 `switch` 陳述句的一部分，主要用來根據變數的值選擇執行的程式碼區塊。這種控制結構使得程式碼更加清晰和易於維護，尤其是在面對多個可能選項的情況下。 ## 文檔 `case` 陳述句的...
Meta Keywords: case, switch, break, 陳述句, default
-->

# C 語言中的 case 陳述句：用於多重選擇的控制結構

## 簡介
在 C 語言中，`case` 陳述句是 `switch` 陳述句的一部分，主要用來根據變數的值選擇執行的程式碼區塊。這種控制結構使得程式碼更加清晰和易於維護，尤其是在面對多個可能選項的情況下。

## 文檔
`case` 陳述句的主要用途是簡化多重條件判斷的過程。與多個 `if` 陳述句相比，`switch-case` 陳述句能夠提高程式的可讀性和執行效率。`case` 陳述句通常和 `switch` 陳述句一起使用，語法如下：

```c
switch (expression) {
    case constant1:
        // 執行的程式碼
        break;
    case constant2:
        // 執行的程式碼
        break;
    default:
        // 預設的執行程式碼
}
```

### 使用方式
1. **表達式**：`switch` 陳述句中的表達式必須返回一個整數類型（`int`）或可轉換為整數的類型。
2. **常數**：每個 `case` 標籤後面跟著一個常數，用來與 `switch` 表達式的值進行比較。
3. **break 陳述句**：在每個 `case` 結束時通常使用 `break` 陳述句來防止繼續執行後面的 `case`。
4. **default 陳述句**：可選的 `default` 陳述句在所有 `case` 都不匹配時執行。

## 範例
以下是使用 `case` 陳述句的基本範例：

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
            printf("不是有效的星期\n");
    }

    return 0;
}
```

在這個範例中，當 `day` 的值為 3 時，程式將輸出「今天是星期三」。

## 解釋
使用 `case` 陳述句時，開發者應注意以下幾點：

1. **重複的 case 標籤**：不允許有重複的 `case` 標籤，否則會導致編譯錯誤。
2. **不使用 break**：如果忘記在某個 `case` 後面加上 `break`，則會發生所謂的「fall-through」行為，這意味著程式會執行後面的 `case` 陳述句，直到遇到 `break` 或 `switch` 結束。
3. **使用整數類型**：`switch` 陳述句中的表達式必須是整數類型或可以被轉換為整數類型的變數，否則將導致編譯錯誤。

## 一句總結
`case` 陳述句是 C 語言中用於簡化多重條件選擇的控制結構，與 `switch` 陳述句一起使用，能有效提高程式碼的可讀性和效率。