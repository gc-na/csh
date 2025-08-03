<!--
Meta Description: # C 語言中的 atan2 函數詳解 ## 概述 `atan2` 函數是 C 語言數學庫中的一個重要數學函數，用於計算給定坐標點的反正切值。它可以幫助用戶在極坐標系中轉換為直角坐標系，並且考慮了象限的影響。 ## 文檔 ### 目的 `atan2` 函數的主要目的是計算一個點 (y, x) 相對於...
Meta Keywords: atan2, double, include, angle1, angle2
-->

# C 語言中的 atan2 函數詳解

## 概述
`atan2` 函數是 C 語言數學庫中的一個重要數學函數，用於計算給定坐標點的反正切值。它可以幫助用戶在極坐標系中轉換為直角坐標系，並且考慮了象限的影響。

## 文檔
### 目的
`atan2` 函數的主要目的是計算一個點 (y, x) 相對於原點的角度，這個角度是從 x 軸正方向測量的，並且範圍在 -π 到 π 之間。這使得 `atan2` 特別適合用於處理坐標系中的方向計算。

### 使用
`atan2` 函數的原型如下：
```c
#include <math.h>

double atan2(double y, double x);
```
- **參數**：
  - `y`：點的 y 坐標。
  - `x`：點的 x 坐標。
  
- **返回值**：
  - 返回值是以弧度表示的角度，範圍在 -π 到 π 之間。

### 詳細資訊
- `atan2` 考慮了 x 和 y 的符號，因此可以正確地返回在不同象限中的角度。
- 當 `x` 為 0 時，`atan2` 會根據 `y` 的符號返回 π/2 或 -π/2。
- 當 `y` 和 `x` 都為 0 時，返回值是未定義的。

## 示例
下面是一些使用 `atan2` 函數的基本示例：

```c
#include <stdio.h>
#include <math.h>

int main() {
    double y1 = 1.0, x1 = 1.0;
    double angle1 = atan2(y1, x1); // 45度 (π/4)

    double y2 = -1.0, x2 = 1.0;
    double angle2 = atan2(y2, x2); // -45度 (-π/4)

    double y3 = 0.0, x3 = 0.0;
    double angle3 = atan2(y3, x3); // 未定義

    printf("Angle1: %f rad\n", angle1);
    printf("Angle2: %f rad\n", angle2);
    printf("Angle3: %f rad\n", angle3); // 注意：未定義情況

    return 0;
}
```

## 解釋
使用 `atan2` 時常見的陷阱包括：
- 在傳遞 `(0, 0)` 作為參數時，返回值是未定義的，因此應避免這種情況。
- 不要將 `atan` 函數與 `atan2` 混淆，因為 `atan` 僅考慮 y/x 的值而不考慮象限。
- 計算結果是以弧度表示的，若需要以度表示，需將結果轉換。

## 一句總結
`atan2` 函數是用於計算從 x 軸到指定點 (y, x) 的角度，並考慮了所有四個象限的數學函數。