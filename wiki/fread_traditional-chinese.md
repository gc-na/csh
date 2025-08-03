<!--
Meta Description: # C 語言中的 fread 函數：實用指南 ## 摘要 `fread` 是 C 語言中用於從檔案中讀取二進位資料的標準函式，其主要功能是將指定數量的資料項讀取到緩衝區中，適用於處理二進位檔案。 ## 文件說明 `fread` 函數的原型如下： ```c size_t fread(void *ptr...
Meta Keywords: fread, file, size_t, itemsread, count
-->

# C 語言中的 fread 函數：實用指南

## 摘要
`fread` 是 C 語言中用於從檔案中讀取二進位資料的標準函式，其主要功能是將指定數量的資料項讀取到緩衝區中，適用於處理二進位檔案。

## 文件說明
`fread` 函數的原型如下：
```c
size_t fread(void *ptr, size_t size, size_t count, FILE *stream);
```

### 目的
`fread` 用於從指定的檔案流中讀取資料，並將讀取到的資料儲存到一個指定的緩衝區中。這個函式特別適合讀取二進位檔案，如圖像、音訊或其他類型的非文本資料。

### 使用方式
- **參數說明**：
  - `ptr`：指向用來儲存讀取資料的緩衝區的指標。
  - `size`：每個資料項的大小（以位元組為單位）。
  - `count`：要讀取的資料項數量。
  - `stream`：指向要讀取的檔案流的指標。

- **返回值**：
  此函式返回實際讀取到的資料項數。如果返回值小於 `count`，則表示達到檔案結尾或發生了錯誤。

## 範例
以下是一個基本的 `fread` 使用範例：

```c
#include <stdio.h>

int main() {
    FILE *file;
    int buffer[10];
    size_t itemsRead;

    // 開啟檔案
    file = fopen("data.bin", "rb");
    if (file == NULL) {
        perror("無法開啟檔案");
        return 1;
    }

    // 讀取資料
    itemsRead = fread(buffer, sizeof(int), 10, file);
    if (itemsRead < 10) {
        if (feof(file)) {
            printf("已達到檔案結尾。\n");
        } else {
            perror("讀取錯誤");
        }
    }

    // 輸出讀取的數據
    for (size_t i = 0; i < itemsRead; i++) {
        printf("讀取的數據[%zu]: %d\n", i, buffer[i]);
    }

    // 關閉檔案
    fclose(file);
    return 0;
}
```

## 解釋
- **常見陷阱**：
  - 確保在讀取之前檔案已正確打開，並處於可讀取模式。
  - 檢查 `fread` 返回的項目數，以確保讀取的資料符合期望。
  - 如果讀取的資料項數量大於檔案中的實際資料量，需處理 `feof` 以確定是否到達檔案結尾。

- **注意事項**：
  - `fread` 不會自動添加結尾符號，這意味著當處理字串時需小心。
  - 應避免在未初始化的指標上使用 `fread`，這可能導致未定義行為。

## 一句總結
`fread` 是 C 語言中用於從檔案流中讀取二進位資料的標準函式，適合處理各類型的二進位檔案。