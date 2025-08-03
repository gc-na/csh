<!--
Meta Description: # putchar 函式：C 語言中的字元輸出函式 ## 概述 `putchar` 是 C 語言中的一個標準函式，用於將單一字元輸出到標準輸出裝置，通常是螢幕。它屬於 `<stdio.h>` 標頭檔，廣泛用於基本的字元輸出操作。 ## 文件說明 `putchar` 函式的主要目的是將指定的字元輸出至...
Meta Keywords: putchar, stdio, int, char, include
-->

# putchar 函式：C 語言中的字元輸出函式

## 概述
`putchar` 是 C 語言中的一個標準函式，用於將單一字元輸出到標準輸出裝置，通常是螢幕。它屬於 `<stdio.h>` 標頭檔，廣泛用於基本的字元輸出操作。

## 文件說明
`putchar` 函式的主要目的是將指定的字元輸出至標準輸出流。函式的原型如下：

```c
int putchar(int char);
```

### 參數
- `char`：要輸出的字元，以整數型別表示，通常是其 ASCII 值。

### 返回值
- 成功時，`putchar` 返回輸出的字元（以 `unsigned char` 型別表示），失敗時返回 `EOF`。

### 使用方式
在使用 `putchar` 時，需包含標頭檔 `stdio.h`，然後可以直接調用函式來輸出字元。例如：

```c
#include <stdio.h>

int main() {
    putchar('A');
    return 0;
}
```

## 範例
以下是使用 `putchar` 的基本範例：

```c
#include <stdio.h>

int main() {
    putchar('H');
    putchar('e');
    putchar('l');
    putchar('l');
    putchar('o');
    putchar('\n'); // 輸出換行
    return 0;
}
```

在這個範例中，程式將字母 "Hello" 輸出到螢幕上，並在最後添加了一個換行符號。

## 解釋
使用 `putchar` 時，有幾個常見的注意事項：

1. **返回值檢查**：雖然 `putchar` 通常不會失敗，但在實際應用中，檢查返回值以確保輸出成功是一個好習慣。
   
2. **輸出字元**：`putchar` 只能輸出單一字元，如需輸出字串，應使用 `printf` 或 `puts`。
   
3. **字符編碼**：確保使用的字元在所選字符編碼中有效，否則可能會導致意外行為。

## 總結
`putchar` 是一個簡單而有效的 C 語言函式，用於輸出單一字元，適合於基礎的字元輸出需求。