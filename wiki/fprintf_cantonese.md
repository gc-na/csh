<!--
Meta Description: # C 語言中的 fprintf 函數：格式化輸出至文件 ## 簡介 `fprintf` 是 C 語言中的一個標準庫函數，用於將格式化輸出寫入指定的文件。它是 `printf` 函數的擴展，允許用戶將格式化字符串和數據寫入檔案，而不僅僅是標準輸出。 ## 文檔 ### 目的 `fprintf` 函數...
Meta Keywords: file, fprintf, int, fopen, fclose
-->

# C 語言中的 fprintf 函數：格式化輸出至文件

## 簡介
`fprintf` 是 C 語言中的一個標準庫函數，用於將格式化輸出寫入指定的文件。它是 `printf` 函數的擴展，允許用戶將格式化字符串和數據寫入檔案，而不僅僅是標準輸出。

## 文檔
### 目的
`fprintf` 函數的主要目的是將格式化的文本輸出到指定的文件流中。這對於需要將程序輸出保存到文件中進行後續處理或記錄時非常有用。

### 使用方法
函數原型如下：
```c
int fprintf(FILE *stream, const char *format, ...);
```

- **參數說明**：
  - `stream`：指向 `FILE` 結構的指針，代表要輸出的文件流。
  - `format`：格式字符串，定義輸出的格式。它可以包含文本、格式指定符（如 `%d`、`%s` 等）以及轉義序列（如 `\n`）。
  - `...`：可變參數，根據格式字符串提供相應類型的數據。

- **返回值**：
  - 如果成功，返回寫入的字符數量；如果出現錯誤，返回負值。

### 詳細說明
在使用 `fprintf` 時，首先需要用 `fopen` 函數打開一個文件，然後將返回的 `FILE` 指針傳遞給 `fprintf`。當完成文件操作後，應使用 `fclose` 函數關閉文件以釋放資源。

## 範例
以下是使用 `fprintf` 的一些基本範例：

### 範例 1：將字符串寫入文件
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "w");
    if (file != NULL) {
        fprintf(file, "Hello, World!\n");
        fclose(file);
    }
    return 0;
}
```

### 範例 2：寫入格式化數據
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("data.txt", "w");
    if (file != NULL) {
        int age = 30;
        fprintf(file, "I am %d years old.\n", age);
        fclose(file);
    }
    return 0;
}
```

### 範例 3：寫入多個變量
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("info.txt", "w");
    if (file != NULL) {
        const char *name = "Alice";
        float height = 5.6;
        fprintf(file, "Name: %s, Height: %.2f\n", name, height);
        fclose(file);
    }
    return 0;
}
```

## 解釋
在使用 `fprintf` 時，有一些常見的陷阱需要注意：
- 確保在寫入之前已成功打開文件，否則 `fprintf` 將無法執行。
- 格式字符串中的占位符必須與傳遞的參數類型匹配，否則可能導致未定義行為。
- 如果在寫入過程中出現錯誤，建議檢查文件流的狀態並進行錯誤處理。

## 總結
`fprintf` 函數是一個強大的工具，用於將格式化的數據寫入文件，對於數據持久化和日誌記錄非常有用。