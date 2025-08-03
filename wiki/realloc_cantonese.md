<!--
Meta Description: # C 語言中的 realloc 函數：動態記憶體重新分配 ## 簡介 `realloc` 是 C 語言中的一個標準函數，用於重新調整先前分配的記憶體區塊的大小。它可以擴展或縮小已經分配的記憶體，並且在需要時會自動移動記憶體。 ## 文檔 ### 目的 `realloc` 的主要目的是根據需要調整之...
Meta Keywords: realloc, int, arr, null, ptr
-->

# C 語言中的 realloc 函數：動態記憶體重新分配

## 簡介
`realloc` 是 C 語言中的一個標準函數，用於重新調整先前分配的記憶體區塊的大小。它可以擴展或縮小已經分配的記憶體，並且在需要時會自動移動記憶體。

## 文檔
### 目的
`realloc` 的主要目的是根據需要調整之前分配的記憶體塊的大小，並保持原有的數據。這在需要動態調整數組或其他數據結構大小時非常有用。

### 使用方法
```c
void* realloc(void* ptr, size_t new_size);
```

- **參數**:
  - `ptr`: 指向之前用 `malloc` 或 `calloc` 分配的記憶體的指針。如果 `ptr` 為 `NULL`，則 `realloc` 的行為等同於 `malloc(new_size)`。
  - `new_size`: 要調整到的新記憶體大小（以字節為單位）。

- **返回值**: 
  - 成功時，返回指向新記憶體區塊的指針。如果無法分配所需大小的記憶體，則返回 `NULL`，原來的記憶體區塊仍然保持不變。

### 詳情
- `realloc` 會嘗試擴展或縮小內存。如果需要移動內存，`realloc` 會自動釋放舊的內存塊，並返回一個指向新內存塊的指針。
- 使用 `realloc` 時，必須小心處理返回的指針，因為如果 `realloc` 失敗，舊的指針仍然有效，但新指針為 `NULL`。

## 示例
### 基本用法示例
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int* arr = (int*)malloc(5 * sizeof(int)); // 分配5個整數的內存
    if (arr == NULL) {
        perror("Failed to allocate memory");
        return 1;
    }

    // 填充數組
    for (int i = 0; i < 5; i++) {
        arr[i] = i + 1;
    }

    // 調整內存大小到10個整數
    int* new_arr = (int*)realloc(arr, 10 * sizeof(int));
    if (new_arr == NULL) {
        free(arr); // 釋放原有內存
        perror("Failed to reallocate memory");
        return 1;
    }
    arr = new_arr; // 更新指針

    // 填充新元素
    for (int i = 5; i < 10; i++) {
        arr[i] = i + 1;
    }

    // 輸出結果
    for (int i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    free(arr); // 最後釋放內存
    return 0;
}
```

## 解釋
- **常見陷阱**: 
  - 在使用 `realloc` 時，如果不檢查返回的指針，可能會導致內存洩漏或使用了無效的內存。
  - 在 `realloc` 失敗的情況下，舊的指針仍然有效，必須確保正確釋放。
  
- **注意事項**: 
  - `realloc` 可能會返回 `NULL`，因此需要檢查返回值。
  - 如果新大小為零，`realloc` 實際上會釋放內存並返回 `NULL`。

## 一句話總結
`realloc` 是 C 語言中用於動態調整已分配內存區塊大小的函數，能有效管理內存使用。