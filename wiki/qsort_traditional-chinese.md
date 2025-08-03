<!--
Meta Description: # C 語言中的 qsort 函數：快速排序的強大工具 ## 簡介 `qsort` 是 C 語言標準函數庫中的一個函數，用於對數組進行排序。這個函數基於快速排序算法，能夠高效地將任意類型的數據進行排序，並且提供了靈活的自定義排序方式。 ## 文檔 ### 目的 `qsort` 函數的主要目的是提供一...
Meta Keywords: qsort, arr, int, const, void
-->

# C 語言中的 qsort 函數：快速排序的強大工具

## 簡介
`qsort` 是 C 語言標準函數庫中的一個函數，用於對數組進行排序。這個函數基於快速排序算法，能夠高效地將任意類型的數據進行排序，並且提供了靈活的自定義排序方式。

## 文檔
### 目的
`qsort` 函數的主要目的是提供一種通用的排序方法，可以對任何類型的數據進行排序，只需提供自定義的比較函數。

### 使用方法
函數原型如下：
```c
void qsort(void *base, size_t num, size_t size, int (*compar)(const void *, const void *));
```

#### 參數說明：
- `base`：指向要排序的數組的指針。
- `num`：數組中的元素數量。
- `size`：每個元素的大小（以字節為單位）。
- `compar`：指向比較函數的指針，該函數用於比較兩個元素，返回值應為負數、零或正數，分別表示第一個元素小於、等於或大於第二個元素。

### 返回值
`qsort` 函數沒有返回值，其排序結果會直接影響傳入的數組。

## 範例
以下是使用 `qsort` 的幾個基本範例：

### 範例 1：排序整數數組
```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return (*(int *)a - *(int *)b);
}

int main() {
    int arr[] = {4, 2, 5, 1, 3};
    size_t arr_size = sizeof(arr) / sizeof(arr[0]);

    qsort(arr, arr_size, sizeof(int), compare);

    for (size_t i = 0; i < arr_size; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
```

### 範例 2：排序字符串數組
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int compare_strings(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

int main() {
    const char *arr[] = {"banana", "apple", "cherry", "date"};
    size_t arr_size = sizeof(arr) / sizeof(arr[0]);

    qsort(arr, arr_size, sizeof(char *), compare_strings);

    for (size_t i = 0; i < arr_size; i++) {
        printf("%s ", arr[i]);
    }
    return 0;
}
```

## 解釋
- **常見陷阱**：確保比較函數正確返回負值、零或正值，否則會導致未定義行為。
- **自定義數據類型**：當排序自定義結構時，需根據結構的比較需求來編寫相應的比較函數。
- **多次排序**：對同一數組多次調用 `qsort` 可能導致性能下降，應謹慎使用。

## 一句總結
`qsort` 是 C 語言中一個高效且靈活的排序工具，能夠通過自定義比較函數對任意類型的數據進行排序。