<!--
Meta Description: # C 語言中的 toupper 函數：將字母轉換為大寫 ## 摘要 `toupper` 函數是 C 語言標準庫中的一個函數，用於將字母字符轉換為其對應的大寫形式。 ## 文檔 ### 目的 `toupper` 函數的主要目的在於將小寫字母轉換為大寫字母，方便在處理字母時保持一致性，尤其是在需要區分...
Meta Keywords: toupper, int, char, lower, non_alpha
-->

# C 語言中的 toupper 函數：將字母轉換為大寫

## 摘要
`toupper` 函數是 C 語言標準庫中的一個函數，用於將字母字符轉換為其對應的大寫形式。

## 文檔
### 目的
`toupper` 函數的主要目的在於將小寫字母轉換為大寫字母，方便在處理字母時保持一致性，尤其是在需要區分大小寫的情況下。

### 使用方法
`toupper` 是在 `<ctype.h>` 標頭檔中定義的。其函數原型如下：

```c
int toupper(int ch);
```

- **參數**：`ch` 是要轉換的字符（以整數形式傳遞）。
- **返回值**：如果 `ch` 是小寫字母，則返回其對應的大寫字母；如果 `ch` 不是小寫字母，則返回原字符。

### 詳細說明
- `toupper` 函數只對小寫字母（'a' 到 'z'）進行轉換。對於其他字符（如數字、標點符號等），`toupper` 會直接返回原字符。
- 此函數對於處理字符串的大小寫轉換非常有用，特別是在需要進行字母比較或格式化時。

## 例子
以下是 `toupper` 函數的基本用法示例：

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char lower = 'g';
    char upper = toupper(lower);
    printf("小寫字母: %c, 大寫字母: %c\n", lower, upper);
    
    char non_alpha = '1';
    printf("非字母字符: %c, 轉換後: %c\n", non_alpha, toupper(non_alpha));

    return 0;
}
```

### 輸出
```
小寫字母: g, 大寫字母: G
非字母字符: 1, 轉換後: 1
```

## 解釋
- **常見問題**：如果傳遞給 `toupper` 的字符不是小寫字母，則它將不會改變該字符。例如，數字或符號將保持不變。
- **範圍問題**：`toupper` 只適用於 ASCII 字符集中的字母。在處理其他字符集（如 UTF-8）時，可能需要其他函數來處理。

## 總結
`toupper` 函數是 C 語言中一個方便的工具，用於將小寫字母轉換為大寫，適合用於字符處理和格式化。