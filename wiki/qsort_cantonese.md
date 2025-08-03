<!--
Meta Description: # C 語言中的 qsort 函數：快速排序的完美選擇 ## 簡介 `qsort` 是 C 語言標準庫中的一個函數，用於對數組進行快速排序。它提供了一種高效的方式來排列數據，適用於各種數據類型。 ## 文檔 ### 目的 `qsort` 函數的主要目的是快速地對數組進行排序。使用者可以自定義排序的準...
Meta Keywords: qsort, int, void, arr, size_t
-->

# C 語言中的 qsort 函數：快速排序的完美選擇

## 簡介
`qsort` 是 C 語言標準庫中的一個函數，用於對數組進行快速排序。它提供了一種高效的方式來排列數據，適用於各種數據類型。

## 文檔
### 目的
`qsort` 函數的主要目的是快速地對數組進行排序。使用者可以自定義排序的準則，從而對不同類型的數據進行排序。

### 語法
```c
void qsort(void *base, size_t num, size_t size, int (*compar)(const void *, const void *));
```

### 參數
- `base`：指向要排序的數組的指針。
- `num`：數組中元素的數量。
- `size`：每個元素的大小（以字節為單位）。
- `compar`：一個比較函數的指針，用於決定元素的排序順序。

### 比較函數
比較函數應返回一個整數：
- 小於零：第一個參數小於第二個參數。
- 等於零：第一個參數等於第二個參數。
- 大於零：第一個參數大於第二個參數。

## 範例
以下是一個簡單的例子，演示如何使用 `qsort` 函數對整數數組進行排序：

```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int arr[] = {5, 3, 2, 8, 1};
    size_t arr_size = sizeof(arr) / sizeof(arr[0]);

    qsort(arr, arr_size, sizeof(int), compare);

    printf("排序後的數組：");
    for (size_t i = 0; i < arr_size; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
```

## 解釋
### 常見陷阱
1. **比較函數的返回值**：確保比較函數正確返回整數值，以避免排序錯誤。
2. **數據類型的大小**：在使用 `sizeof` 獲取元素大小時，必須確保使用正確的數據類型。

### 注意事項
- `qsort` 可能會對相同值的元素進行不穩定排序，這意味著相同的元素在排序後的順序可能會改變。
- 使用 `qsort` 時，確保提供的數組具有足夠的大小，避免越界訪問。

## 一句總結
`qsort` 是 C 語言中一個高效的排序函數，允許用戶自定義排序準則以對數組進行排序。