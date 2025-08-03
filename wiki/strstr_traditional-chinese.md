<!--
Meta Description: # 在 C 語言中使用 strstr 函數：尋找子字串的利器 ## 概述 `strstr` 函數是 C 語言中用於查找子字串的標準函數，屬於字串處理的一部分。它可以有效地在一個字串中尋找另一個字串的首次出現位置。 ## 文件說明 ### 功能 `strstr` 函數用於在給定的字串中查找指定的子字串...
Meta Keywords: strstr, char, needle, haystack, const
-->

# 在 C 語言中使用 strstr 函數：尋找子字串的利器

## 概述
`strstr` 函數是 C 語言中用於查找子字串的標準函數，屬於字串處理的一部分。它可以有效地在一個字串中尋找另一個字串的首次出現位置。

## 文件說明
### 功能
`strstr` 函數用於在給定的字串中查找指定的子字串，並返回指向第一次出現的該子字串的指針。如果找不到子字串，則該函數返回 NULL。

### 語法
```c
char *strstr(const char *haystack, const char *needle);
```

### 參數
- `haystack`：要搜尋的主要字串。
- `needle`：要查找的子字串。

### 回傳值
- 若成功找到子字串，則返回指向該子字串在主要字串中的首次出現位置的指針。
- 若未找到，則返回 NULL。

### 使用範例
以下是一個使用 `strstr` 的基本範例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Hello, World!";
    const char *needle = "World";

    char *result = strstr(haystack, needle);
    if (result) {
        printf("找到子字串: %s\n", result);
    } else {
        printf("未找到子字串。\n");
    }

    return 0;
}
```

### 輸出
```
找到子字串: World!
```

## 解釋
- **常見問題**：使用 `strstr` 時，需確保 `needle` 字串不為空。如果 `needle` 為空字串，根據標準，`strstr` 會返回 `haystack` 的指針。
- **性能考量**：`strstr` 函數在查找過程中可能會涉及多次比較，對於長字串或多次調用，性能可能受到影響。
- **大小寫敏感**：`strstr` 是大小寫敏感的，因此 "hello" 和 "Hello" 被視為不同的字串。

## 總結
`strstr` 是 C 語言中一個強大且常用的函數，用於查找字串中的子字串。