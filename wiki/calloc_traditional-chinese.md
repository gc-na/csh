<!--
Meta Description: # calloc：C 語言中的動態記憶體分配函數 ## 概述 `calloc` 是 C 語言中的一個標準庫函數，用於動態分配記憶體。它的主要功能是分配一塊初始化為零的記憶體區域，以便用於儲存數據結構，如陣列或結構體。 ## 文件說明 `calloc` 函數的原型定義在 `<stdlib.h>` 標頭...
Meta Keywords: calloc, arr, size_t, int, null
-->

# calloc：C 語言中的動態記憶體分配函數

## 概述
`calloc` 是 C 語言中的一個標準庫函數，用於動態分配記憶體。它的主要功能是分配一塊初始化為零的記憶體區域，以便用於儲存數據結構，如陣列或結構體。

## 文件說明
`calloc` 函數的原型定義在 `<stdlib.h>` 標頭檔中，其語法如下：

```c
void* calloc(size_t num, size_t size);
```

### 參數
- **num**：需要分配的元素個數。
- **size**：每個元素的大小（以位元組為單位）。

### 返回值
`calloc` 返回一個指向分配記憶體區域的指標。如果分配失敗，則返回 `NULL`。

### 目的
`calloc` 的主要目的在於：
- 同時分配多個元素的記憶體。
- 自動將分配的記憶體初始化為零，這在某些情況下能避免不必要的錯誤。

## 使用範例
以下是 `calloc` 的基本使用範例：

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    size_t n = 5;

    // 使用 calloc 分配記憶體
    arr = (int*) calloc(n, sizeof(int));

    if (arr == NULL) {
        printf("記憶體分配失敗\n");
        return 1;
    }

    // 輸出每個元素的值（應該全部為零）
    for (size_t i = 0; i < n; i++) {
        printf("arr[%zu] = %d\n", i, arr[i]);
    }

    // 釋放已分配的記憶體
    free(arr);
    return 0;
}
```

## 解釋
在使用 `calloc` 時，開發者需注意以下幾點：

1. **記憶體釋放**：使用 `calloc` 分配的記憶體必須在不再需要時使用 `free` 釋放，以防止記憶體洩漏。
   
2. **錯誤處理**：應始終檢查 `calloc` 返回的指標是否為 `NULL`，以確保記憶體分配成功。

3. **初始化**：`calloc` 會自動將所分配的記憶體初始化為零，這與 `malloc` 不同，後者分配的記憶體內容未定義。

4. **多次分配**：可以使用 `calloc` 分配多個元素，但需確保不會超出系統的記憶體限制，導致分配失敗。

## 一句話總結
`calloc` 是 C 語言中的一個動態記憶體分配函數，能夠分配並初始化為零的記憶體區域。