<!--
Meta Description: # C 語言中的 extern 關鍵字：功能與用法 ## 概述 `extern` 是 C 語言中的一個關鍵字，主要用於聲明變數或函數的外部鏈接性。這意味著使用 `extern` 可以讓不同的檔案共享變數和函數，從而實現模組化編程。 ## 文檔 `extern` 關鍵字的主要用途是告訴編譯器某個變數或...
Meta Keywords: extern, globalvar, void, myfunction, int
-->

# C 語言中的 extern 關鍵字：功能與用法

## 概述
`extern` 是 C 語言中的一個關鍵字，主要用於聲明變數或函數的外部鏈接性。這意味著使用 `extern` 可以讓不同的檔案共享變數和函數，從而實現模組化編程。

## 文檔
`extern` 關鍵字的主要用途是告訴編譯器某個變數或函數是在其他檔案中定義的，這樣可以避免重複定義的錯誤。它有助於管理多個檔案中的變數和函數，使代碼更加整潔和可維護。

### 用法
1. **聲明變數**：使用 `extern` 可以在一個檔案中聲明在其他檔案中定義的變數。
   ```c
   extern int globalVar;
   ```

2. **聲明函數**：同樣，`extern` 也可以用來聲明在其他檔案中定義的函數，通常不需要顯式使用 `extern`，因為函數聲明默認是外部的。
   ```c
   extern void myFunction();
   ```

### 詳細說明
- 在 C 語言中，變數的鏈接性有兩種：內部鏈接和外部鏈接。內部鏈接的變數只能在其定義的檔案中使用，而外部鏈接的變數則可以在其他檔案中使用。
- 使用 `extern` 聲明的變數不會分配存儲空間，而是告訴編譯器在其他地方找尋該變數的定義。
- 當多個檔案需要使用同一變數時，通常會在一個檔案中定義該變數，然後在其他檔案中使用 `extern` 進行聲明。

## 示例
### 例子 1：聲明外部變數
**檔案：file1.c**
```c
#include <stdio.h>

int globalVar = 10; // 定義變數

void display() {
    printf("Global Variable: %d\n", globalVar);
}
```

**檔案：file2.c**
```c
#include <stdio.h>

extern int globalVar; // 聲明外部變數

void modify() {
    globalVar = 20; // 修改外部變數
}
```

### 例子 2：聲明外部函數
**檔案：file1.c**
```c
#include <stdio.h>

void myFunction() {
    printf("Hello from myFunction!\n");
}
```

**檔案：file2.c**
```c
#include <stdio.h>

extern void myFunction(); // 聲明外部函數

int main() {
    myFunction(); // 調用外部函數
    return 0;
}
```

## 解釋
- **常見陷阱**：如果在聲明外部變數時沒有正確地定義該變數，將會導致連結錯誤。確保每個 `extern` 聲明都有相對應的定義。
- **作用域問題**：`extern` 僅用於聲明變數或函數的存在，並不改變其作用域。如果變數的作用域是局部的，則無法在其他檔案中訪問。
- **初始化注意**：`extern` 聲明不能初始化變數，必須在其他檔案中定義並初始化。

## 一句話總結
`extern` 關鍵字在 C 語言中用於聲明外部鏈接的變數和函數，允許跨檔案共享資源。