<!--
Meta Description: # 在 C 語言中的 strstr 函數：搜索子字串的完美工具 ## 概述 `strstr` 是 C 語言標準庫中的一個函數，用於搜索一個字串中是否包含另一個子字串。它在處理字符串時非常有用，尤其在需要查找特定模式或子字串的情況下。 ## 文件說明 `strstr` 函數的目的在於尋找一個字串（稱為...
Meta Keywords: strstr, needle, char, haystack, const
-->

# 在 C 語言中的 strstr 函數：搜索子字串的完美工具

## 概述
`strstr` 是 C 語言標準庫中的一個函數，用於搜索一個字串中是否包含另一個子字串。它在處理字符串時非常有用，尤其在需要查找特定模式或子字串的情況下。

## 文件說明
`strstr` 函數的目的在於尋找一個字串（稱為「子字串」）在另一個字串（稱為「主字串」）中的首次出現位置。該函數的原型定義在 `<string.h>` 標頭文件中。

### 語法
```c
char *strstr(const char *haystack, const char *needle);
```

### 參數
- `haystack`：指向需要搜索的主字串的指針。
- `needle`：指向需要搜索的子字串的指針。

### 返回值
- 如果找到 `needle`，則返回指向 `haystack` 中首次出現 `needle` 的位置的指針。
- 如果未找到 `needle`，則返回 `NULL`。

## 示例
### 基本用法
以下是 `strstr` 的一個簡單示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Hello, world!";
    const char *needle = "world";

    char *result = strstr(haystack, needle);
    if (result) {
        printf("找到子字串: %s\n", result);
    } else {
        printf("未找到子字串。\n");
    }
    return 0;
}
```

### 另一個示例
這裡是一個搜索不存在的子字串的示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Hello, world!";
    const char *needle = "C programming";

    char *result = strstr(haystack, needle);
    if (result) {
        printf("找到子字串: %s\n", result);
    } else {
        printf("未找到子字串。\n");
    }
    return 0;
}
```

## 解釋
使用 `strstr` 時，最常見的問題是：
- **大小寫敏感性**：`strstr` 是大小寫敏感的，這意味著 "hello" 和 "Hello" 被視為不同的字串。
- **空指針**：傳遞 `NULL` 作為 `haystack` 或 `needle` 會導致未定義的行為。應該始終檢查指針是否為 `NULL`。
- **性能問題**：對於非常長的字串，`strstr` 的性能可能會受影響，特別是在多次調用時。考慮使用其他字符串處理方法以提高效率。

## 一句總結
`strstr` 是 C 語言中用於查找子字串的強大函數，能有效地定位字符序列的出現位置。