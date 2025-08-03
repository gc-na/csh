<!--
Meta Description: # C 語言中的 tolower 函數：轉換字元為小寫 ## 摘要 `tolower` 是 C 語言標準庫中的一個函數，用於將大寫字母轉換為小寫字母，並對非字母字元不做改變。這個函數在處理字串和字符時，特別是在需要進行大小寫比較的場景中非常有用。 ## 文件說明 ### 函數原型 ```c #inc...
Meta Keywords: tolower, str, include, ctype, int
-->

# C 語言中的 tolower 函數：轉換字元為小寫

## 摘要
`tolower` 是 C 語言標準庫中的一個函數，用於將大寫字母轉換為小寫字母，並對非字母字元不做改變。這個函數在處理字串和字符時，特別是在需要進行大小寫比較的場景中非常有用。

## 文件說明
### 函數原型
```c
#include <ctype.h>

int tolower(int c);
```

### 參數
- `c`：要轉換的字符，通常是一個整數，代表字符的 ASCII 值。

### 返回值
- 返回轉換後的字元，如果 `c` 是大寫字母，則返回其相對應的小寫字母；如果 `c` 不是大寫字母，則直接返回原字符。

### 用途
`tolower` 常用於文本處理的場合，例如：
- 在比較字符串時，將所有字符轉換為小寫以實現不區分大小寫的比較。
- 清理用戶輸入時，統一字母的大小寫格式。

## 範例
以下是幾個 `tolower` 函數的基本用法示例：

### 範例 1：單一字符轉換
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'A';
    char lower = tolower(ch);
    printf("轉換前: %c, 轉換後: %c\n", ch, lower);
    return 0;
}
```

### 範例 2：字符串的大小寫轉換
```c
#include <stdio.h>
#include <ctype.h>

void convertToLower(char *str) {
    while (*str) {
        *str = tolower(*str);
        str++;
    }
}

int main() {
    char str[] = "Hello World!";
    convertToLower(str);
    printf("轉換後的字符串: %s\n", str);
    return 0;
}
```

## 解釋
### 常見陷阱
1. **非字母字符**：`tolower` 函數對於非字母字符（如數字或標點符號）不會進行轉換，這可能會導致一些不預期的行為。
2. **多字節字符**：如果處理的是多字節字符（如 UTF-8 字符集中的某些字符），`tolower` 可能無法正確處理。此函數僅適用於單字節字符（即 ASCII 字符）。
3. **未包含標頭文件**：使用 `tolower` 函數時，必須包含 `<ctype.h>` 標頭文件，否則會導致編譯錯誤。

## 一句總結
`tolower` 函數是用於將大寫字母轉換為小寫字母的 C 語言標準庫函數，對於文本處理和比較非常有用。