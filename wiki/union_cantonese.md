<!--
Meta Description: # C 語言中的聯合 (union)：用途與範例 ## 概述 在 C 語言中，聯合（union）是一種數據結構，允許在同一記憶體位置儲存不同類型的數據。這使得程序員能夠節省記憶體，並根據需要在不同的數據類型之間切換。 ## 文檔 ### 目的 聯合的主要目的是提供一種方式來使用相同的記憶體空間來處理...
Meta Keywords: data, union, intvalue, floatvalue, printf
-->

# C 語言中的聯合 (union)：用途與範例

## 概述
在 C 語言中，聯合（union）是一種數據結構，允許在同一記憶體位置儲存不同類型的數據。這使得程序員能夠節省記憶體，並根據需要在不同的數據類型之間切換。

## 文檔
### 目的
聯合的主要目的是提供一種方式來使用相同的記憶體空間來處理不同的數據類型。每個聯合的成員共用同一塊記憶體，這樣可以有效地利用內存。

### 用法
聯合的基本語法如下：

```c
union union_name {
    data_type1 member1;
    data_type2 member2;
    // ...
};
```

例如，定義一個名為 `Data` 的聯合，可以存儲整數或浮點數：

```c
union Data {
    int intValue;
    float floatValue;
};
```

要使用聯合，您需要定義聯合變數，然後可以根據需要設置和讀取相應的成員：

```c
union Data data;

data.intValue = 10; // 設置整數值
printf("整數值: %d\n", data.intValue);

data.floatValue = 3.14; // 設置浮點數值
printf("浮點數值: %f\n", data.floatValue);
```

注意：當您設置聯合的某個成員時，其它成員的值將不再有效。

## 範例
以下是使用聯合的簡單示例：

```c
#include <stdio.h>

union Data {
    int intValue;
    float floatValue;
};

int main() {
    union Data data;

    data.intValue = 5;
    printf("整數值: %d\n", data.intValue);
    
    data.floatValue = 10.5;
    printf("浮點數值: %f\n", data.floatValue); // 此時 intValue 的值未定義

    return 0;
}
```

## 解釋
### 常見陷阱
- **記憶體覆蓋**：因為所有成員共用相同的記憶體空間，所以只應該在需要的時候使用聯合的特定成員，否則會導致不可預測的行為。
- **未初始化的成員**：當聯合被創建時，只有第一個成員的值會被初始化，其他成員的值是未定義的。

### 附加說明
- 聯合的大小由其最大成員的大小決定。
- 聯合可以包含其他聯合或結構體，這樣可以實現更複雜的數據結構。

## 一句總結
聯合（union）是 C 語言中一種有效利用記憶體的數據結構，允許在同一記憶體空間中存儲不同類型的數據。