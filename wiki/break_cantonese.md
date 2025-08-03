<!--
Meta Description: # C 語言中的 "break" 語句：用於控制流程的關鍵字 ## 概述 "break" 是 C 語言中的一個關鍵字，用於終止一個循環或 switch 語句的執行。它能夠幫助開發者更靈活地控制程式的執行流程。 ## 文檔 ### 目的 "break" 語句的主要目的是使程式在特定條件下立即退出當前循...
Meta Keywords: break, switch, printf, int, while
-->

# C 語言中的 "break" 語句：用於控制流程的關鍵字

## 概述
"break" 是 C 語言中的一個關鍵字，用於終止一個循環或 switch 語句的執行。它能夠幫助開發者更靈活地控制程式的執行流程。

## 文檔
### 目的
"break" 語句的主要目的是使程式在特定條件下立即退出當前循環或 switch 語句。這樣的功能使得程式能夠在滿足特定條件時，避免不必要的迭代或選擇。

### 用法
"break" 語句通常用於以下情況：
- 在 **for**、**while**、或 **do-while** 循環中，當滿足某種條件時終止循環。
- 在 **switch** 語句中，終止一個案例的執行，避免自動進入下一個案例。

```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break; // 當 i 等於 5 時，終止循環
        }
        printf("%d\n", i);
    }
    return 0;
}
```

### 詳細說明
- **結構**：在循環或 switch 語句中，可以直接使用 "break" 語句。
- **範圍**：只會終止最近的循環或 switch 語句，對於嵌套結構，只影響最內層的結構。
- **替代方案**：在某些情況下，可以使用標籤和 `goto` 語句來代替 "break"，但這種做法通常不被推薦，因為會降低程式的可讀性。

## 示例
### 基本使用範例
以下是使用 "break" 語句的基本範例：

```c
#include <stdio.h>

int main() {
    int n;

    printf("請輸入一個正整數 (0 以退出): ");
    while (1) {
        scanf("%d", &n);
        if (n == 0) {
            break; // 當 n 為 0 時，終止循環
        }
        printf("你輸入的數字是：%d\n", n);
    }
    return 0;
}
```

### 在 switch 語句中的使用
以下是 "break" 在 switch 語句中的使用範例：

```c
#include <stdio.h>

int main() {
    int choice;
    printf("請選擇一個數字 (1-3): ");
    scanf("%d", &choice);

    switch (choice) {
        case 1:
            printf("你選擇了 1\n");
            break; // 終止 switch 語句
        case 2:
            printf("你選擇了 2\n");
            break; // 終止 switch 語句
        case 3:
            printf("你選擇了 3\n");
            break; // 終止 switch 語句
        default:
            printf("無效的選擇\n");
    }
    return 0;
}
```

## 解釋
### 常見陷阱
- **忽略使用 "break"**：在 switch 語句中如果忘記使用 "break"，程式將會繼續執行下一個案例，這可能導致意外的行為。
- **誤用在多層循環**：在嵌套循環中，"break" 只會終止最內層的循環，這可能造成開發者混淆。

## 一句總結
"break" 是 C 語言中用於控制循環和 switch 語句執行流程的重要工具，能在特定條件下終止當前結構的執行。