<!--
Meta Description: # C 語言中的 strtok 函數：字串分割工具 ## 概述 `strtok` 是 C 語言標準庫中用來將字串分割成一系列標記的函數。這個函數對於處理以特定分隔符分隔的字串特別有用，比如 CSV 文件或自然語言處理。 ## 文檔 ### 目的 `strtok` 函數的主要目的是將一個字串根據指定的...
Meta Keywords: strtok, char, null, token, str
-->

# C 語言中的 strtok 函數：字串分割工具

## 概述
`strtok` 是 C 語言標準庫中用來將字串分割成一系列標記的函數。這個函數對於處理以特定分隔符分隔的字串特別有用，比如 CSV 文件或自然語言處理。

## 文檔
### 目的
`strtok` 函數的主要目的是將一個字串根據指定的分隔符進行分割，並返回分割後的每個標記。這使得在處理結構化字串時變得更加方便。

### 使用方式
`strtok` 的基本語法如下：
```c
char *strtok(char *str, const char *delim);
```
- **參數**：
  - `str`：要被分割的字串。在第一次調用時，這個參數需要傳入待處理的字串，後續調用時應該傳入 `NULL`。
  - `delim`：一組用作分隔符的字元。

- **返回值**：當找到一個標記時，`strtok` 返回指向該標記的指針；如果沒有更多標記，則返回 `NULL`。

### 詳細說明
`strtok` 會在原始字串中插入 `\0`（空字符）來終止每個標記，並且會修改原始字串。這意味著如果需要保留原始字串，應該在使用前進行複製。

## 示例
以下是 `strtok` 的基本用法示例：
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "C,Programming,Language";
    char *token;

    // 第一次調用，傳入字串
    token = strtok(str, ",");
    
    // 繼續獲取標記
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, ",");
    }

    return 0;
}
```
### 輸出：
```
C
Programming
Language
```

## 解釋
### 常見陷阱
1. **修改原始字串**：`strtok` 會直接修改原始字串，這可能導致原始資料丟失。
2. **多次調用**：在分割過程中，必須在後續調用中傳入 `NULL`，以指示函數從上次停止的地方繼續。
3. **非線性分隔符**：如果分隔符包含在字串中，`strtok` 將會視為分隔標記，並可能造成意外的結果。

## 一句總結
`strtok` 是 C 語言中用來根據指定分隔符分割字串的函數，能有效簡化字串處理過程。