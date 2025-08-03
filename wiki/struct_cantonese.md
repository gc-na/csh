<!--
Meta Description: # C 語言中的 struct：結構體的詳細指南 ## 簡介 在 C 語言中，`struct`（結構體）是一種用來將不同類型的數據組合在一起的數據結構，適合用於創建複雜的數據類型，以便更好地管理和操作數據。 ## 文件 `struct` 的主要目的是提供一種方式來定義用戶自定義的數據類型。這使得開發...
Meta Keywords: struct, john, name, student1, person
-->

# C 語言中的 struct：結構體的詳細指南

## 簡介
在 C 語言中，`struct`（結構體）是一種用來將不同類型的數據組合在一起的數據結構，適合用於創建複雜的數據類型，以便更好地管理和操作數據。

## 文件
`struct` 的主要目的是提供一種方式來定義用戶自定義的數據類型。這使得開發者能夠將相關的變量組合在一起，使程式碼更加清晰和高效。

### 用法
要定義一個結構體，使用 `struct` 關鍵字，然後指定結構體名稱和其成員。例如：

```c
struct Person {
    char name[50];
    int age;
    float height;
};
```

這段代碼定義了一個名為 `Person` 的結構體，包含三個成員：姓名、年齡和身高。要創建這個結構體的實例，可以這樣做：

```c
struct Person john;
```

接著，你可以通過點運算符來訪問結構體的成員：

```c
strcpy(john.name, "John Doe");
john.age = 30;
john.height = 5.9;
```

### 詳細說明
1. **成員變量**：結構體的成員可以是不同數據類型的變量，這使得它們非常靈活。
2. **內存佈局**：結構體的內存佈局由其成員的順序和大小決定。這可能會導致內存對齊問題。
3. **嵌套結構**：結構體可以包含其他結構體，這樣可以組織更複雜的數據。

## 示例
以下是一個簡單的示例，演示如何使用結構體來存儲和顯示學生的資料：

```c
#include <stdio.h>
#include <string.h>

struct Student {
    char name[50];
    int id;
};

int main() {
    struct Student student1;
    
    strcpy(student1.name, "Alice");
    student1.id = 101;
    
    printf("學生名字: %s\n", student1.name);
    printf("學生編號: %d\n", student1.id);
    
    return 0;
}
```

## 解釋
- **常見陷阱**：在使用結構體時，需特別注意內存對齊問題，這可能會影響性能和數據存取的效率。
- **結構體大小**：使用 `sizeof` 操作符可以查看結構體的大小，但記住這可能會受到對齊的影響。
- **初始化**：結構體可以在定義時進行初始化，例如：
  
  ```c
  struct Person john = {"John Doe", 30, 5.9};
  ```

## 總結
`struct` 是 C 語言中強大的數據結構工具，使用它可以有效地組織和管理複雜數據。