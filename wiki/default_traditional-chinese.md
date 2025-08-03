<!--
Meta Description: # C 語言中的 "default" 關鍵字 ## 概要 在 C 語言中，`default` 是一個關鍵字，主要用於 `switch` 陳述中，指示在沒有匹配的 `case` 時執行的預設代碼區塊。 ## 文檔 ### 目的 `default` 關鍵字的主要目的是提供一種機制，當 `switch` ...
Meta Keywords: default, case, switch, break, 陳述中
-->

# C 語言中的 "default" 關鍵字

## 概要
在 C 語言中，`default` 是一個關鍵字，主要用於 `switch` 陳述中，指示在沒有匹配的 `case` 時執行的預設代碼區塊。

## 文檔
### 目的
`default` 關鍵字的主要目的是提供一種機制，當 `switch` 陳述中的所有 `case` 都不匹配時，執行某一特定的代碼區塊。這對於處理預期之外的情況非常有用。

### 使用方法
`default` 通常是放在 `switch` 陳述的最後一個位置。其語法如下：

```c
switch (expression) {
    case constant1:
        // 執行代碼
        break;
    case constant2:
        // 執行代碼
        break;
    default:
        // 當所有 case 都不匹配時執行的代碼
}
```

在上述語法中，`expression` 是要評估的表達式，而 `constant1` 和 `constant2` 是可供比較的常量。如果 `expression` 的值不等於任何 case 的常量，則會執行 `default` 區塊的代碼。

## 範例
以下是使用 `default` 的基本範例：

```c
#include <stdio.h>

int main() {
    int number = 3;

    switch (number) {
        case 1:
            printf("數字是 1\n");
            break;
        case 2:
            printf("數字是 2\n");
            break;
        default:
            printf("數字不是 1 或 2\n");
            break;
    }

    return 0;
}
```

在這個範例中，由於 `number` 的值是 3，將會輸出 "數字不是 1 或 2"。

## 解釋
### 常見問題
1. **`default` 位置**：`default` 可以放在 `switch` 陳述的任何位置，雖然通常放在最後。即使將其放在中間，程式仍然可以正常運行，但通常這樣做不符合編碼慣例。
   
2. **缺少 `break`**：如果 `default` 區塊中沒有 `break` 語句，控制流將會繼續進入後續的 `case` 陳述，這可能導致意想不到的行為。

3. **多個 `default`**：在同一個 `switch` 陳述中，不能有多個 `default`。如果有多個，將會導致編譯錯誤。

### 附加說明
`default` 的使用有助於提高代碼的可讀性和可維護性，因為它清楚地表明當所有其他情況都不符合時應該執行的代碼。

## 一句總結
在 C 語言中，`default` 關鍵字用於 `switch` 陳述中，以處理所有不匹配的情況。