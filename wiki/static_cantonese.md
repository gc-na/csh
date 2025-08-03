<!--
Meta Description: # C 語言中的 "static" 關鍵字：用途與使用 ## 簡介 在 C 語言中，`static` 是一個關鍵字，用於定義變量和函數的存儲類別。它影響變量的生命週期和可見範圍，並在多個用途中發揮重要作用。 ## 文件說明 `static` 關鍵字的主要目的是控制變量的存儲方式和生存時間。當一個變量...
Meta Keywords: static, int, void, function, total
-->

# C 語言中的 "static" 關鍵字：用途與使用

## 簡介
在 C 語言中，`static` 是一個關鍵字，用於定義變量和函數的存儲類別。它影響變量的生命週期和可見範圍，並在多個用途中發揮重要作用。

## 文件說明
`static` 關鍵字的主要目的是控制變量的存儲方式和生存時間。當一個變量被聲明為 `static` 時，該變量的生命週期將持續到程序結束，而不是在每次進入其作用域時被創建和銷毀。此外，`static` 變量在其所在的文件內部是私有的，這意味著它不會被其他文件訪問。

### 用法
1. **靜態局部變量**：
   當一個變量在函數內部被聲明為 `static` 時，該變量只會被初始化一次，之後在函數的多次調用中會保留其值。

   ```c
   void function() {
       static int count = 0; // 只會初始化一次
       count++;
       printf("%d\n", count);
   }
   ```

2. **靜態全局變量**：
   當一個變量在全局範圍內被聲明為 `static` 時，該變量的可見範圍限於定義它的文件，其他文件無法訪問。

   ```c
   static int globalVar = 10; // 只在此文件可見
   ```

3. **靜態函數**：
   使用 `static` 關鍵字來定義函數意味著該函數只能在定義它的文件中被調用。

   ```c
   static void helperFunction() {
       // 僅在此文件中有效
   }
   ```

## 例子
以下是 `static` 關鍵字的簡單使用範例：

### 靜態局部變量示例
```c
#include <stdio.h>

void countCalls() {
    static int callCount = 0; // 靜態局部變量
    callCount++;
    printf("Function called %d times\n", callCount);
}

int main() {
    countCalls(); // 輸出: Function called 1 times
    countCalls(); // 輸出: Function called 2 times
    countCalls(); // 輸出: Function called 3 times
    return 0;
}
```

### 靜態全局變量示例
```c
#include <stdio.h>

static int total = 0; // 靜態全局變量

void add(int value) {
    total += value;
}

void printTotal() {
    printf("Total: %d\n", total);
}

int main() {
    add(5);
    add(10);
    printTotal(); // 輸出: Total: 15
    return 0;
}
```

## 解釋
使用 `static` 可能會遇到一些常見的陷阱：
- **初始化**：靜態變量只會初始化一次，這可能導致錯誤的預期行為，特別是在多次調用函數時。
- **作用域限制**：靜態全局變量和靜態函數無法在其他文件中訪問，這可能會影響代碼的模塊化和重用性。
- **內存使用**：靜態變量佔用的內存會在程序運行期間一直存在，因此過度使用可能會導致內存浪費。

## 一句話總結
`static` 關鍵字在 C 語言中用於控制變量和函數的生命週期及可見範圍，對提高程序的結構性和效率具有重要意義。