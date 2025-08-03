<!--
Meta Description: # fseek 函數在 C 語言中的用法 ## 簡介 `fseek` 是 C 語言中的一個標準函數，用於在文件中移動檔案指標，這對於隨機存取文件內容非常重要。 ## 文檔 `fseek` 函數的主要目的是改變一個打開的文件的當前讀寫位置。它的語法如下： ```c int fseek(FILE *st...
Meta Keywords: fseek, file, int, offset, whence
-->

# fseek 函數在 C 語言中的用法

## 簡介
`fseek` 是 C 語言中的一個標準函數，用於在文件中移動檔案指標，這對於隨機存取文件內容非常重要。

## 文檔
`fseek` 函數的主要目的是改變一個打開的文件的當前讀寫位置。它的語法如下：

```c
int fseek(FILE *stream, long offset, int whence);
```

### 參數說明
- `stream`：指向 FILE 結構的指針，該結構表示要操作的文件。
- `offset`：從 `whence` 指定的位置開始偏移的字節數。
- `whence`：指定起始位置，可以是以下三個常量之一：
  - `SEEK_SET`：從檔案開頭開始計算偏移。
  - `SEEK_CUR`：從當前檔案指標位置開始計算偏移。
  - `SEEK_END`：從檔案末尾開始計算偏移。

### 返回值
若成功，`fseek` 返回 0；若失敗，返回 -1，並且設置 `errno` 來指示錯誤類型。

## 示例
以下是使用 `fseek` 的基本示例：

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Unable to open file");
        return 1;
    }

    // 將指標移動到文件的開始位置
    fseek(file, 0, SEEK_SET);

    // 將指標移動到文件的第 10 個字節
    fseek(file, 10, SEEK_SET);

    // 讀取第 10 個字節
    char ch = fgetc(file);
    printf("Character at position 10: %c\n", ch);

    fclose(file);
    return 0;
}
```

## 解釋
使用 `fseek` 時，有幾個常見的注意事項：
- 確保在使用 `fseek` 之前，文件已經成功打開。
- `offset` 可以是負值，但必須確保不會超出文件的範圍，否則會導致未定義行為。
- 在使用 `fseek` 之後，使用 `ftell` 函數可以檢查當前的檔案指標位置。
- 對於二進制文件，請確保以二進制模式打開文件，否則可能會導致意外行為。

## 總結
`fseek` 函數是 C 語言中用於隨機存取文件的關鍵工具，能夠有效地管理檔案指標的位置。