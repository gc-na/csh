<!--
Meta Description: # C 語言中的 strtok 函數：字串切割的利器 ## 簡介 `strtok` 函數是 C 語言標準庫中用於將字串分割成多個子字串的工具，常用於處理以特定分隔符分隔的字串，方便開發者進行資料解析和處理。 ## 文檔 ### 功能 `strtok` 函數用於將字串分割為一系列的標記（tokens）...
Meta Keywords: strtok, char, token, str, null
-->

# C 語言中的 strtok 函數：字串切割的利器

## 簡介
`strtok` 函數是 C 語言標準庫中用於將字串分割成多個子字串的工具，常用於處理以特定分隔符分隔的字串，方便開發者進行資料解析和處理。

## 文檔
### 功能
`strtok` 函數用於將字串分割為一系列的標記（tokens），根據指定的分隔符進行切割。它會返回指向每個標記的指針，直到沒有更多的標記可供返回。

### 語法
```c
char *strtok(char *str, const char *delim);
```

### 參數
- **str**: 要分割的字串。如果這是第一次調用 `strtok`，則應傳入待處理的字串；如果是後續調用，則應傳入 `NULL`。
- **delim**: 一個包含所有可能的分隔符的字串。

### 返回值
`strtok` 返回指向找到的標記的指針。如果沒有更多的標記，則返回 `NULL`。

### 注意事項
- `strtok` 會修改原始字串，在分隔符處插入 `'\0'` 字元，因此在使用後原始字串將不再可用。
- `strtok` 是非線程安全的，因為它使用靜態內部狀態來儲存當前位置。

## 範例
以下是一個使用 `strtok` 的基本範例，展示如何分割字串：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello, world; this is a test.";
    char *token;

    // 使用空格和逗號作為分隔符
    token = strtok(str, " ,;.");

    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, " ,;.");
    }

    return 0;
}
```

### 輸出
```
Hello
world
this
is
a
test
```

## 解釋
### 常見陷阱
- **原始字串修改**: 使用 `strtok` 時必須注意，原始字串會被修改。若需保留原始字串，請先將其複製到另一個變數中。
- **非線程安全**: `strtok` 無法在多線程環境中安全使用。若在多線程中需要類似功能，可以考慮使用 `strtok_r` 函數，這是一個可重入的版本。

### 額外說明
在處理多個分隔符時，`strtok` 會將相連的分隔符視為單一分隔符，這意味著如果在字串中有多個連續的分隔符，將不會返回空標記。

## 一行總結
`strtok` 是 C 語言中用於將字串分割為多個子字串的函數，透過指定的分隔符有效解析字串內容。