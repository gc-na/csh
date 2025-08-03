<!--
Meta Description: # calloc 函數在 C 語言中的使用 ## 概述 `calloc` 是 C 語言中的一個內存分配函數，用於分配指定數量的內存並初始化為零。它是標準庫中的一部分，主要用於動態內存管理。 ## 文檔 ### 目的 `calloc` 函數的主要目的是分配指定數量的內存塊，每個塊的大小由用戶指定，並且...
Meta Keywords: calloc, int, arr, null, malloc
-->

# calloc 函數在 C 語言中的使用

## 概述
`calloc` 是 C 語言中的一個內存分配函數，用於分配指定數量的內存並初始化為零。它是標準庫中的一部分，主要用於動態內存管理。

## 文檔
### 目的
`calloc` 函數的主要目的是分配指定數量的內存塊，每個塊的大小由用戶指定，並且所有分配的內存塊都會自動初始化為零。

### 語法
```c
void* calloc(size_t num, size_t size);
```

### 參數
- `num`: 要分配的內存塊數量。
- `size`: 每個內存塊的大小（以字節為單位）。

### 返回值
如果內存分配成功，`calloc` 會返回一個指向分配內存的指針；如果失敗，則返回 `NULL`。

### 使用範例
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    int n = 5;

    // 使用 calloc 分配內存
    arr = (int*)calloc(n, sizeof(int));

    if (arr == NULL) {
        printf("內存分配失敗\n");
        return 1;
    }

    // 輸出初始化的數組
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]); // 所有元素應該為 0
    }

    // 釋放分配的內存
    free(arr);
    return 0;
}
```

## 解釋
### 常見陷阱
1. **未檢查返回值**: 使用 `calloc` 時，必須檢查返回的指針是否為 `NULL`，以避免空指針解引用。
2. **內存洩漏**: 忘記釋放使用 `calloc` 分配的內存會導致內存洩漏，應使用 `free` 來釋放內存。
3. **初始化的數據**: 使用 `calloc` 分配的內存會被初始化為零，但如果使用 `malloc` 則不會。

### 附加說明
`calloc` 在某些情況下比 `malloc` 更有用，特別是當需要確保內存被初始化為零時。它的性能可能會略低於 `malloc`，因為它需要初始化內存。

## 一句總結
`calloc` 是 C 語言中用於分配並初始化內存的函數，使得開發者能夠有效管理動態內存。