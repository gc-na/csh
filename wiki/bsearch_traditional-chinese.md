<!--
Meta Description: # C 語言中的 bsearch 函數：高效的二分搜尋法 ## 概述 `bsearch` 是 C 語言標準庫中的一個函數，用於在已排序的陣列中執行二分搜尋，以快速查找特定元素。 ## 文件說明 ### 目的 `bsearch` 函數的主要目的是提供一種高效的方法來查找一個元素在已排序陣列中的位置，時...
Meta Keywords: bsearch, int, void, const, key
-->

# C 語言中的 bsearch 函數：高效的二分搜尋法

## 概述
`bsearch` 是 C 語言標準庫中的一個函數，用於在已排序的陣列中執行二分搜尋，以快速查找特定元素。

## 文件說明

### 目的
`bsearch` 函數的主要目的是提供一種高效的方法來查找一個元素在已排序陣列中的位置，時間複雜度為 O(log n)，比線性搜尋更快。

### 使用方法
`bsearch` 函數的語法如下：

```c
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, int (*compar)(const void*, const void*));
```

#### 參數
- `key`: 指向要查找的元素的指針。
- `base`: 指向已排序陣列的指針。
- `nmemb`: 陣列中的元素數量。
- `size`: 每個元素的大小（以位元組為單位）。
- `compar`: 指向比較函數的指針，該函數用於比較 `key` 和陣列中的元素。

#### 返回值
- 如果找到目標元素，則返回指向該元素的指針。
- 如果未找到，則返回 `NULL`。

### 包含的標頭檔
使用 `bsearch` 函數時，必須包含以下標頭檔：

```c
#include <stdlib.h>
```

## 範例

### 基本用法範例
以下是一個使用 `bsearch` 的範例，查找整數陣列中的元素：

```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
    int key = 5;
    int* item = (int*)bsearch(&key, arr, sizeof(arr) / sizeof(arr[0]), sizeof(int), compare);

    if (item != NULL) {
        printf("找到元素：%d\n", *item);
    } else {
        printf("元素未找到。\n");
    }

    return 0;
}
```

## 解釋

### 常見問題
1. **陣列必須是已排序的**：`bsearch` 只能用於已排序的陣列，若陣列未排序，則結果將不可靠。
2. **比較函數的定義**：比較函數必須正確實現，返回值必須符合以下規則：
   - 若 `a < b`，返回負值。
   - 若 `a == b`，返回零。
   - 若 `a > b`，返回正值。
3. **指針類型轉換**：在比較函數中，必須將 `void*` 轉換為正確的數據類型。

## 一句總結
`bsearch` 函數提供了一種高效的方式來在已排序陣列中查找元素，時間複雜度為 O(log n)。