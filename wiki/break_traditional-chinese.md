<!--
Meta Description: # C 語言中的 "break" 语句：用法与示例 ## 摘要 在 C 語言中，`break` 语句是一個控制流指令，用於立即跳出當前的循環或 switch 語句，從而終止循環的執行或 switch 的選擇。 ## 文件說明 `break` 语句在 C 語言中的主要作用是控制程序的流向。當程序執行到...
Meta Keywords: break, switch, case, number, int
-->

# C 語言中的 "break" 语句：用法与示例

## 摘要
在 C 語言中，`break` 语句是一個控制流指令，用於立即跳出當前的循環或 switch 語句，從而終止循環的執行或 switch 的選擇。

## 文件說明
`break` 语句在 C 語言中的主要作用是控制程序的流向。當程序執行到 `break` 語句時，將立即退出所在的循環（例如 `for`、`while`、`do while`）或 `switch` 語句。這使得程序能夠在滿足特定條件時提前終止循環或選擇結構。

### 用法
`break` 的基本語法如下：
```c
break;
```

### 詳細說明
- `break` 语句通常用於循環結構中，用來根據特定條件退出循環。
- 在 `switch` 語句中，`break` 用來終止該 `case` 的執行，避免執行到後續的 `case`。

## 示例
以下是 `break` 语句的基本用法示例：

### 示例 1：在 for 循環中使用 `break`
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break; // 當 i 等於 5 時退出循環
        }
        printf("%d\n", i);
    }
    return 0;
}
```
輸出：
```
0
1
2
3
4
```

### 示例 2：在 switch 語句中使用 `break`
```c
#include <stdio.h>

int main() {
    int number = 2;
    switch (number) {
        case 1:
            printf("Number is 1\n");
            break; // 結束此 case 的執行
        case 2:
            printf("Number is 2\n");
            break; // 結束此 case 的執行
        default:
            printf("Number is unknown\n");
    }
    return 0;
}
```
輸出：
```
Number is 2
```

## 解釋
在使用 `break` 语句時，需要注意以下幾點：
- 如果在嵌套的循環中使用 `break`，僅會退出最近的那一層循環，其他外層循環仍然會繼續執行。
- 在 `switch` 語句中，未使用 `break` 會導致“fall-through”行為，即執行當前 `case` 之後，繼續執行後續 `case` 的代碼，這在某些情況下可能會導致意外的行為。

## 一句總結
`break` 语句在 C 語言中用於立即退出循環或 switch 結構，控制程序的執行流程。