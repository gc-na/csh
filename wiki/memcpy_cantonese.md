<!--
Meta Description: # memcpy：C 語言中的記憶體拷貝函數 ## 概要 `memcpy` 是 C 語言中的一個標準庫函數，用於將一段記憶體的內容從一個位置拷貝到另一個位置。它在處理字節數據時特別有用，並且常用於數據結構和緩衝區操作。 ## 文檔 ### 目的 `memcpy` 的主要目的是高效地將指定大小的記憶體...
Meta Keywords: memcpy, dest, src, void, 應使用
-->

# memcpy：C 語言中的記憶體拷貝函數

## 概要
`memcpy` 是 C 語言中的一個標準庫函數，用於將一段記憶體的內容從一個位置拷貝到另一個位置。它在處理字節數據時特別有用，並且常用於數據結構和緩衝區操作。

## 文檔
### 目的
`memcpy` 的主要目的是高效地將指定大小的記憶體區域從源位置複製到目標位置。

### 使用方法
`memcpy` 函數的原型如下：

```c
void *memcpy(void *dest, const void *src, size_t n);
```

#### 參數
- `dest`：目標記憶體的位置（指向要拷貝到的目標）。
- `src`：源記憶體的位置（指向要拷貝的來源）。
- `n`：要拷貝的字節數。

#### 返回值
`memcpy` 返回目標指針 `dest`。

### 注意事項
- `memcpy` 不會檢查源和目標區域是否重疊。如果源和目標區域重疊，應使用 `memmove` 函數。
- `memcpy` 不會初始化目標區域，因此使用前應確保目標區域已經分配好內存並且是有效的。

## 範例
以下是使用 `memcpy` 的基本範例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[] = "Hello, World!";
    char dest[20];

    memcpy(dest, src, strlen(src) + 1);  // 包括結束符 '\0'
    
    printf("Copied string: %s\n", dest);
    return 0;
}
```

這段代碼將字符串 "Hello, World!" 從 `src` 拷貝到 `dest`，並打印出來。

## 解釋
### 常見的陷阱
1. **重疊區域**：如果 `src` 和 `dest` 重疊，結果未定，可能會導致數據損壞。應使用 `memmove` 來處理這種情況。
2. **未分配內存**：在使用 `memcpy` 前，確保 `dest` 指向的內存已經分配好，否則會導致未定義行為。
3. **不正確的字節數**：確保 `n` 的值正確，超出範圍可能導致內存溢出或錯誤的數據拷貝。

## 一句總結
`memcpy` 是一個高效的記憶體拷貝函數，用於在 C 語言中將數據從一個位置複製到另一個位置。