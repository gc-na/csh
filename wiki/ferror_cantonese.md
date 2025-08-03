<!--
Meta Description: # ferror 函數：C 語言中的錯誤檢測 ## Synopsis `ferror` 是 C 語言中的一個標準函數，用於檢查流的錯誤狀態，特別是在文件操作中，確保程式能夠正確處理輸入和輸出過程中的錯誤。 ## Documentation ### 目的 `ferror` 函數的主要目的是檢查與文件流...
Meta Keywords: ferror, file, 100, include, stdio
-->

# ferror 函數：C 語言中的錯誤檢測

## Synopsis
`ferror` 是 C 語言中的一個標準函數，用於檢查流的錯誤狀態，特別是在文件操作中，確保程式能夠正確處理輸入和輸出過程中的錯誤。

## Documentation
### 目的
`ferror` 函數的主要目的是檢查與文件流相關的錯誤。當你對文件進行讀取或寫入操作時，有時可能會發生錯誤，使用 `ferror` 可以幫助你確認這些錯誤的存在。

### 使用方法
```c
#include <stdio.h>

int ferror(FILE *stream);
```

- **參數**：
  - `stream`：指向 `FILE` 結構的指針，該結構表示要檢查的文件流。

- **返回值**：
  - 如果流中有錯誤，`ferror` 返回一個非零值；如果沒有錯誤，則返回 0。

### 詳細說明
- `ferror` 函數通常與其他文件操作函數一起使用，例如 `fopen`, `fread`, `fwrite`, `fclose` 等。當你執行這些操作後，可以使用 `ferror` 檢查是否發生錯誤。
- 確保在使用 `ferror` 之前，文件流已經正確地打開，並且進行了相應的操作。

## Examples
以下是一些基本用法示例：

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Error opening file");
        return -1;
    }

    char buffer[100];
    if (fread(buffer, sizeof(char), 100, file) < 100) {
        if (ferror(file)) {
            printf("Error reading from file\n");
        } else {
            printf("End of file reached\n");
        }
    }

    fclose(file);
    return 0;
}
```

在上面的範例中，當讀取文件時，`ferror` 檢查是否發生錯誤。

## Explanation
- **常見問題**：如果在使用 `ferror` 之前未對流進行任何操作，則返回的結果可能不準確。
- **注意事項**：在處理錯誤時，應該考慮使用 `clearerr` 函數來重置流的錯誤狀態，以便未來的操作能夠正常進行。

## One Line Summary
`ferror` 函數用於檢查 C 語言中文件流的錯誤狀態，以確保正確處理文件操作中的錯誤。