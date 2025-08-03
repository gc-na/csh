<!--
Meta Description: # C 語言中的 realloc 函數：動態記憶體重新分配的最佳實踐 ## 概要 `realloc` 是 C 語言中的一個標準庫函數，用於調整已分配記憶體的大小。它可以擴展或縮小先前使用 `malloc` 或 `calloc` 函數分配的記憶體區塊，並在需要時自動移動到新的記憶體位置。 ## 文檔 ...
Meta Keywords: realloc, null, arr, int, malloc
-->

# C 語言中的 realloc 函數：動態記憶體重新分配的最佳實踐

## 概要
`realloc` 是 C 語言中的一個標準庫函數，用於調整已分配記憶體的大小。它可以擴展或縮小先前使用 `malloc` 或 `calloc` 函數分配的記憶體區塊，並在需要時自動移動到新的記憶體位置。

## 文檔
### 目的
`realloc` 函數的主要目的是管理動態記憶體，允許程序在執行時根據需求調整記憶體的大小。這對於不確定大小的數據結構（例如動態數組）特別有用。

### 用法
`realloc` 函數的語法如下：

```c
void* realloc(void* ptr, size_t new_size);
```

- **參數**：
  - `ptr`：指向先前分配的記憶體區塊的指針，可以是 `malloc`、`calloc` 或 `realloc` 返回的指針。如果 `ptr` 為 `NULL`，則相當於調用 `malloc`。
  - `new_size`：要分配的新記憶體大小（以字節為單位）。

- **返回值**：如果成功，返回指向新記憶體區塊的指針。如果失敗，返回 `NULL`，並且原有的記憶體區塊不會被釋放。

- **注意事項**：成功調整大小後，原有的記憶體區塊可能會被釋放或移動，因此需要使用返回的指針來訪問新記憶體區塊。

## 範例
### 基本使用範例

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // 初始分配記憶體
    int* arr = (int*)malloc(5 * sizeof(int));
    if (arr == NULL) {
        perror("Failed to allocate memory");
        return 1;
    }

    // 使用 realloc 調整大小
    arr = (int*)realloc(arr, 10 * sizeof(int));
    if (arr == NULL) {
        perror("Failed to reallocate memory");
        return 1;
    }

    // 使用新的記憶體區塊
    for (int i = 0; i < 10; i++) {
        arr[i] = i + 1;
        printf("%d ", arr[i]);
    }

    // 釋放記憶體
    free(arr);
    return 0;
}
```

## 解釋
### 常見陷阱與注意事項
1. **NULL 檢查**：使用 `realloc` 後必須檢查返回值是否為 `NULL`，以確保記憶體擴展成功。
2. **失敗時的行為**：如果 `realloc` 失敗，原有的記憶體區塊仍然存在，並不會被釋放。因此應該在分配新的記憶體指針之前保存原有指針的值。
3. **傳遞 NULL 指針**：如果 `ptr` 為 `NULL`，`realloc` 的行為就如同 `malloc`，這是一個簡單的方式來分配新記憶體。
4. **記憶體洩漏**：如果未正確處理 `realloc` 返回的指針，可能會導致記憶體洩漏。

## 單行總結
`realloc` 是 C 語言中用於動態調整記憶體大小的函數，能夠擴展或縮小已分配的記憶體空間。