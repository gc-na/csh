<!--
Meta Description: # C 語言中的 case 陳述式：用於有效的條件控制 ## 概要 在 C 語言中，`case` 陳述式用於 `switch` 陳述式中，以對多個可能的值進行條件判斷，從而選擇相應的執行路徑。 ## 文件說明 `case` 陳述式是一種控制結構，通常與 `switch` 陳述式搭配使用。它允許程序根...
Meta Keywords: case, break, switch, expression, printf
-->

# C 語言中的 case 陳述式：用於有效的條件控制

## 概要
在 C 語言中，`case` 陳述式用於 `switch` 陳述式中，以對多個可能的值進行條件判斷，從而選擇相應的執行路徑。

## 文件說明
`case` 陳述式是一種控制結構，通常與 `switch` 陳述式搭配使用。它允許程序根據變量的值執行不同的代碼塊。這種結構使得多重條件判斷變得簡單且可讀性強。`case` 陳述式的基本語法如下：

```c
switch (expression) {
    case constant1:
        // 當 expression 等於 constant1 時執行的代碼
        break;
    case constant2:
        // 當 expression 等於 constant2 時執行的代碼
        break;
    // 可以有多個 case
    default:
        // 當 expression 的值不匹配任何 case 時執行的代碼
}
```

### 用法
- `expression` 是一個整數表達式或字符，`switch` 將根據其值選擇匹配的 `case`。
- 每個 `case` 後面跟著一個常量值，這些值必須是唯一的。
- `break` 陳述式用於終止 `switch` 結構的執行，防止執行落入下一個 `case`。
- `default` 是可選的，當沒有匹配的 `case` 時執行。

## 範例
以下是一個使用 `case` 陳述式的簡單例子：

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
        default:
            printf("未知的日期\n");
    }
    
    return 0;
}
```

在這個例子中，當 `day` 的值為 3 時，程式會輸出 "星期三"。

## 解釋
使用 `case` 陳述式時，有幾個常見的陷阱需要注意：
- **漏掉 break**：如果在某個 `case` 中忘記加上 `break`，程式會繼續執行下一個 `case`，這稱為“fall-through”行為，可能導致意外結果。
- **case 值必須是常量**：`case` 陳述式中的值必須是編譯時已知的常量，無法使用變量或運算結果。
- **不支持浮點數**：`case` 陳述式僅支持整數和字符，對於浮點數則不適用。

## 一句總結
C 語言中的 `case` 陳述式用於 `switch` 控制結構，能有效管理多個條件分支。