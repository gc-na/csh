<!--
Meta Description: # 在C語言中的 "extern" 關鍵字：用途及示例 ## 簡介 "extern" 是C語言中的一個關鍵字，用於聲明變量或函數的外部連接性。這意味著變量或函數的定義可能位於其他文件中，從而允許跨文件訪問和共享。 ## 文檔 ### 目的 "extern" 主要用於告訴編譯器某個變量或函數在其他地方...
Meta Keywords: extern, count, file2, file1, include
-->

# 在C語言中的 "extern" 關鍵字：用途及示例

## 簡介
"extern" 是C語言中的一個關鍵字，用於聲明變量或函數的外部連接性。這意味著變量或函數的定義可能位於其他文件中，從而允許跨文件訪問和共享。

## 文檔
### 目的
"extern" 主要用於告訴編譯器某個變量或函數在其他地方被定義。這對於大型項目特別重要，因為它使得不同的源文件能夠互相引用，從而實現模塊化的編程風格。

### 用法
在C語言中，"extern" 可以用於變量和函數：
- **變量**：當你想在一個文件中使用另一個文件中定義的變量時，可以使用 "extern" 來聲明該變量。
- **函數**：所有函數的默認連接性都是外部的，但使用 "extern" 聲明可以使代碼更具可讀性。

#### 基本語法
```c
extern type variable_name;  // 變量聲明
extern return_type function_name(parameter_types);  // 函數聲明
```

## 範例
### 變量範例
**文件1：`file1.c`**
```c
#include <stdio.h>

int count = 10;  // 定義變量

void display() {
    printf("Count: %d\n", count);
}
```

**文件2：`file2.c`**
```c
#include <stdio.h>

extern int count;  // 聲明外部變量

int main() {
    printf("Count from file2: %d\n", count);
    return 0;
}
```

在這個例子中，`file2.c` 使用了在 `file1.c` 中定義的變量 `count`。

### 函數範例
**文件1：`file1.c`**
```c
#include <stdio.h>

void greet() {
    printf("Hello, World!\n");
}
```

**文件2：`file2.c`**
```c
#include <stdio.h>

extern void greet();  // 聲明外部函數

int main() {
    greet();  // 調用外部函數
    return 0;
}
```

在此示例中，`file2.c` 調用了在 `file1.c` 中定義的 `greet` 函數。

## 解釋
使用 "extern" 時，開發者需注意以下幾點：
- **未初始化的變量**：如果你聲明一個 `extern` 變量而沒有對其進行初始化，則在使用該變量之前必須確保它在某處被正確定義和初始化。
- **重複聲明**：在同一作用域內，重複聲明同一變量或函數可能會導致編譯錯誤。
- **與靜態變量的區別**：靜態變量只在定義它的文件內部可見，而 `extern` 變量則可以在多個文件之間共享。

## 一句總結
"extern" 關鍵字在C語言中用於聲明外部變量和函數，以便在不同文件之間共享和引用。