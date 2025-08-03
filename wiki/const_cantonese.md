<!--
Meta Description: # C 語言中的 const 變量：使用與特性詳解 ## 簡介 `const` 是 C 語言中的一個關鍵字，用於聲明常量變量，這意味著一旦賦值後，該變量的值將無法被改變。 ## 文檔 ### 目的 `const` 的主要目的是提高代碼的可讀性和安全性，通過防止意外修改變量的值來減少錯誤。 ### 用...
Meta Keywords: const, int, max_value, ptr, value
-->

# C 語言中的 const 變量：使用與特性詳解

## 簡介
`const` 是 C 語言中的一個關鍵字，用於聲明常量變量，這意味著一旦賦值後，該變量的值將無法被改變。

## 文檔
### 目的
`const` 的主要目的是提高代碼的可讀性和安全性，通過防止意外修改變量的值來減少錯誤。

### 用法
在 C 語言中，`const` 可以修飾基本數據類型、指針及結構體等，語法格式如下：
```c
const data_type variable_name = value;
```
例如：
```c
const int max_value = 100;
```
這表示 `max_value` 的值為 100，並且在後續的代碼中不能被改變。

### 詳細說明
1. **修飾基本數據類型**：可以用於整數、浮點數等基本數據類型。
2. **修飾指針**：`const` 可以修飾指針本身或者指針所指向的內容。
   - 修飾指針本身的例子：`const int *ptr;` 表示指針 `ptr` 可以指向整數，但不能通過 `ptr` 來修改整數的值。
   - 修飾指針所指向內容的例子：`int *const ptr;` 表示 `ptr` 本身的地址不能改變，但可以改變指針所指向的數據。

## 示例
```c
#include <stdio.h>

int main() {
    const int max_value = 10;
    // max_value = 20; // 這將導致編譯錯誤

    const int *ptr = &max_value;
    // *ptr = 20; // 這將導致編譯錯誤

    int value = 20;
    int *const const_ptr = &value;
    *const_ptr = 30; // 這是合法的，value 現在是 30
    // const_ptr = &max_value; // 這將導致編譯錯誤

    printf("max_value: %d\n", max_value);
    printf("value: %d\n", value);
    return 0;
}
```

## 解釋
1. **常見陷阱**：初學者經常會誤認為 `const` 會保護指針本身不被更改。實際上，修飾指針本身和修飾指針指向的數據是兩種不同的用法。
2. **對性能的影響**：使用 `const` 不會顯著影響性能，但會改善代碼的可讀性與維護性。
3. **結構體中的 `const`**：在結構體中使用 `const` 可以確保結構體的一部分在初始化後不被改變。

## 一句總結
`const` 是 C 語言中的關鍵字，用於聲明常量變量，防止其值在後續代碼中被意外修改。