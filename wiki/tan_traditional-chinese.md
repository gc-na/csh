<!--
Meta Description: # 在C語言中的tan函數：三角函數的計算 ## 摘要 `tan`函數是C標準庫中的一個數學函數，用於計算一個角度的正切值。此函數在數學、工程和科學計算中被廣泛應用。 ## 文件說明 `tan`函數的主要目的是計算給定弧度的正切值。它屬於C標準數學庫`math.h`，並且需要在使用時包含此標頭文件。...
Meta Keywords: tan, m_pi, include, double, math
-->

# 在C語言中的tan函數：三角函數的計算

## 摘要
`tan`函數是C標準庫中的一個數學函數，用於計算一個角度的正切值。此函數在數學、工程和科學計算中被廣泛應用。

## 文件說明
`tan`函數的主要目的是計算給定弧度的正切值。它屬於C標準數學庫`math.h`，並且需要在使用時包含此標頭文件。正切函數是三角函數之一，定義為對應的正弦值與餘弦值的比值。

### 語法
```c
#include <math.h>

double tan(double x);
```

### 參數
- `x`：一個以弧度為單位的浮點數，表示要計算正切的角度。

### 返回值
`tan`函數返回給定角度的正切值。如果輸入為無限大或導致未定義的情況，函數將返回`NaN`（Not a Number）。

## 示例
以下是使用`tan`函數的基本範例：

### 示例1：計算正切值
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 4; // 45度
    double result = tan(angle);
    printf("tan(45度) = %f\n", result);
    return 0;
}
```

### 示例2：計算多個角度的正切值
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angles[] = {0, M_PI / 6, M_PI / 4, M_PI / 3, M_PI / 2};
    for(int i = 0; i < 5; i++) {
        printf("tan(%f) = %f\n", angles[i], tan(angles[i]));
    }
    return 0;
}
```

## 解釋
使用`tan`函數時，開發者需要注意以下幾點：
- **弧度與角度**：`tan`函數接收的參數必須是弧度。如果使用角度，需要將其轉換為弧度（例如，角度乘以`M_PI/180`）。
- **未定義的結果**：當輸入為`π/2 + kπ`（k為整數）時，正切值會變為無限大，這會導致程序返回`NaN`。
- **數學庫連結**：在編譯時，確保鏈接數學庫，通常需要在命令中添加`-lm`選項，例如：`gcc program.c -o program -lm`。

## 總結
`tan`函數在C語言中是一個基本的數學函數，能夠有效地計算給定弧度的正切值，是數學計算中不可或缺的工具。