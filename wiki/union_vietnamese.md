<!--
Meta Description: # Union trong ngôn ngữ lập trình C: Cấu trúc dữ liệu mạnh mẽ ## Tóm tắt Union trong C là một kiểu dữ liệu cho phép lưu trữ nhiều kiểu dữ liệu khác nha...
Meta Keywords: một, union, data, dụng, trường
-->

# Union trong ngôn ngữ lập trình C: Cấu trúc dữ liệu mạnh mẽ

## Tóm tắt
Union trong C là một kiểu dữ liệu cho phép lưu trữ nhiều kiểu dữ liệu khác nhau trong cùng một vùng nhớ, giúp tiết kiệm bộ nhớ và tối ưu hóa hiệu suất khi làm việc với nhiều loại dữ liệu.

## Tài liệu
Union là một kiểu dữ liệu đặc biệt trong ngôn ngữ lập trình C, cho phép bạn định nghĩa một biến có thể chứa nhiều kiểu dữ liệu khác nhau nhưng chỉ có thể sử dụng một kiểu tại một thời điểm. Cú pháp để định nghĩa một union tương tự như cấu trúc (struct), với từ khóa `union` được sử dụng để khai báo.

### Cú pháp
```c
union TênUnion {
    KiểuDữLiệu1 trường1;
    KiểuDữLiệu2 trường2;
    ...
};
```

### Mục đích
Mục đích chính của union là tiết kiệm bộ nhớ. Khi bạn biết rằng bạn chỉ cần sử dụng một trong các kiểu dữ liệu tại một thời điểm nhất định, union là lựa chọn tốt hơn so với struct, vì struct sẽ cấp phát bộ nhớ cho tất cả các trường cùng một lúc.

### Sử dụng
Để sử dụng union, bạn có thể khai báo một biến của union và truy cập các trường của nó giống như với struct. Tuy nhiên, bạn nên lưu ý rằng chỉ có một trường có thể được sử dụng tại một thời điểm, và kích thước của union sẽ bằng kích thước của trường lớn nhất.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng union trong C:

```c
#include <stdio.h>

union Data {
    int i;
    float f;
    char str[20];
};

int main() {
    union Data data;

    data.i = 10;
    printf("data.i = %d\n", data.i);

    data.f = 220.5;
    printf("data.f = %.1f\n", data.f);

    strcpy(data.str, "Hello");
    printf("data.str = %s\n", data.str);

    return 0;
}
```

### Kết quả
```
data.i = 10
data.f = 220.5
data.str = Hello
```

## Giải thích
Khi bạn sử dụng union, hãy nhớ rằng việc gán giá trị cho một trường sẽ ghi đè lên giá trị của các trường khác. Trong ví dụ trên:
- Khi bạn gán `data.i = 10`, chỉ có trường `i` được sử dụng.
- Khi bạn gán `data.f = 220.5`, trường `i` bị ghi đè và không còn sử dụng được.
- Cuối cùng, khi gán `data.str`, cả hai trường `i` và `f` cũng bị ghi đè.

### Những điều cần lưu ý
- Đảm bảo rằng bạn chỉ sử dụng một trường tại một thời điểm để tránh các lỗi không mong muốn.
- Kích thước của union được xác định bởi kích thước của trường lớn nhất.
- Union không tự động kiểm tra kiểu dữ liệu đang được sử dụng, vì vậy bạn cần phải quản lý nó một cách cẩn thận.

## Tóm tắt một câu
Union trong C cho phép lưu trữ nhiều kiểu dữ liệu trong cùng một vùng nhớ, tiết kiệm bộ nhớ nhưng cần được sử dụng cẩn thận để tránh ghi đè không mong muốn.