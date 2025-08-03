<!--
Meta Description: # C 語言中的 fscanf 函數詳解 ## 簡介 `fscanf` 是 C 語言中用於從文件中讀取格式化數據的函數。它的功能類似於 `scanf`，但主要用於處理文件輸入。 ## 文件說明 `fscanf` 的主要目的在於從指定的文件流中讀取數據，並根據給定的格式字符串將這些數據存儲到變量中。這...
Meta Keywords: fscanf, file, age, name, int
-->

# C 語言中的 fscanf 函數詳解

## 簡介
`fscanf` 是 C 語言中用於從文件中讀取格式化數據的函數。它的功能類似於 `scanf`，但主要用於處理文件輸入。

## 文件說明
`fscanf` 的主要目的在於從指定的文件流中讀取數據，並根據給定的格式字符串將這些數據存儲到變量中。這使得開發者能夠靈活地從文件中提取所需的數據。

### 語法
```c
int fscanf(FILE *stream, const char *format, ...);
```

### 參數
- `stream`：指向 FILE 結構的指針，表示要讀取的文件流。
- `format`：格式字符串，指示如何解析輸入數據。
- `...`：根據格式字符串提供的變量地址，用於存儲讀取的數據。

### 返回值
`fscanf` 返回成功讀取的項目數量。如果出現錯誤或到達文件結尾，則返回 EOF 或者小於格式字符串中指定的項目數量。

## 示例
以下是 `fscanf` 基本用法的示例：

```c
#include <stdio.h>

int main() {
    FILE *file;
    int age;
    char name[50];

    file = fopen("data.txt", "r");
    if (file == NULL) {
        printf("無法打開文件。\n");
        return 1;
    }

    fscanf(file, "%s %d", name, &age);
    printf("姓名: %s, 年齡: %d\n", name, age);

    fclose(file);
    return 0;
}
```
在這個示例中，`fscanf` 從 "data.txt" 文件中讀取一個字符串和一個整數，並將其存儲到 `name` 和 `age` 變量中。

## 解釋
使用 `fscanf` 時需要注意以下幾點：
- 格式字符串必須與文件中的數據格式嚴格對應，否則可能導致讀取錯誤。
- 確保文件已成功打開，否則 `fscanf` 將無法讀取數據。
- 使用 `&` 取地址符號時，只需對於基本數據類型（如整數）使用，對於字符串類型不需要。

## 總結
`fscanf` 是一個用於從文件中格式化讀取數據的強大工具，能夠靈活地處理多種數據類型。