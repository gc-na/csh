<!--
Meta Description: # C 語言中的 strncpy 函數詳解 ## 簡介 `strncpy` 是 C 語言中的一個字符串處理函數，主要用於將一個字符串的部分內容複製到另一個字符串中。它提供了對字符串複製過程的更高控制，特別是在需要限制複製的字符數量時。 ## 文檔 ### 目的 `strncpy` 函數的主要目的是將...
Meta Keywords: dest, strncpy, src, char, include
-->

# C 語言中的 strncpy 函數詳解

## 簡介
`strncpy` 是 C 語言中的一個字符串處理函數，主要用於將一個字符串的部分內容複製到另一個字符串中。它提供了對字符串複製過程的更高控制，特別是在需要限制複製的字符數量時。

## 文檔
### 目的
`strncpy` 函數的主要目的是將源字符串中的最多 n 個字符複製到目標字符串中，這樣可以防止緩衝區溢出。

### 語法
```c
char *strncpy(char *dest, const char *src, size_t n);
```

### 參數
- `dest`: 目標字符串，將存儲複製內容的地方。
- `src`: 源字符串，從中複製內容的來源。
- `n`: 要複製的最大字符數。

### 返回值
`strncpy` 返回 `dest` 的指針。

### 使用說明
- 當 `src` 的長度小於 `n` 時，`dest` 將用 `src` 的內容填充，然後用空字符填充剩餘的部分。
- 當 `src` 的長度大於或等於 `n` 時，僅複製 `n` 個字符，並且 `dest` 不會自動以空字符結尾。

## 範例
### 基本用法示例
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20];
    const char *src = "Hello, World!";
    
    // 複製前 5 個字符
    strncpy(dest, src, 5);
    dest[5] = '\0';  // 手動添加空字符以結束字符串
    printf("Result: %s\n", dest); // 輸出: Result: Hello

    return 0;
}
```

### 示例 2: 溢出情況
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[5];
    const char *src = "Hello, World!";
    
    // 複製前 10 個字符
    strncpy(dest, src, 10);
    dest[4] = '\0';  // 手動添加空字符以防止未結束字符串
    printf("Result: %s\n", dest); // 輸出: Result: Hell

    return 0;
}
```

## 解釋
### 常見問題
- **未自動添加空字符**: `strncpy` 不會自動在目標字符串的末尾添加空字符，這可能導致字符串在使用時出現未定義的行為。開發者應該在必要時手動添加。
- **緩衝區溢出**: 雖然 `strncpy` 允許用戶指定要複製的字符數量，但如果目標緩衝區不足以容納這些字符（特別是沒有添加空字符的情況下），仍然可能會導致溢出問題。

### 附加說明
在使用 `strncpy` 時，建議開發者仔細考慮目標緩衝區的大小及其安全性，並且盡量在複製後檢查字符串的結束符，避免潛在的安全漏洞。

## 一句話總結
`strncpy` 是一個用於安全複製字符串的函數，但開發者需小心手動添加結束符以避免未定義行為。