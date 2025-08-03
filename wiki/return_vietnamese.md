<!--
Meta Description: # Câu lệnh "return" trong ngôn ngữ lập trình C: Tác dụng và Cách sử dụng ## Tóm tắt Câu lệnh "return" trong ngôn ngữ lập trình C được sử dụng để kết t...
Meta Keywords: hàm, return, trả, câu, lệnh
-->

# Câu lệnh "return" trong ngôn ngữ lập trình C: Tác dụng và Cách sử dụng

## Tóm tắt
Câu lệnh "return" trong ngôn ngữ lập trình C được sử dụng để kết thúc một hàm và trả về giá trị cho hàm gọi nó. Đây là một phần quan trọng trong việc kiểm soát luồng chương trình và quản lý các giá trị trả về từ các hàm.

## Tài liệu
### Mục đích
Câu lệnh "return" có hai chức năng chính: 
1. Kết thúc hàm đang thực thi.
2. Trả về một giá trị cho hàm gọi, nếu hàm đó được định nghĩa với kiểu trả về khác `void`.

### Cách sử dụng
Cú pháp cơ bản của câu lệnh "return" là:
```c
return giá_trị;
```
- `giá_trị`: Giá trị mà bạn muốn trả về từ hàm. Giá trị này phải tương thích với kiểu dữ liệu mà hàm đã được định nghĩa.

Ví dụ:
```c
int cộng(int a, int b) {
    return a + b; // Trả về tổng của a và b
}
```
Nếu bạn định nghĩa hàm với kiểu trả về `void`, bạn có thể sử dụng câu lệnh `return` mà không cần theo sau là giá trị:
```c
void in_thong_bao() {
    printf("Xin chào!\n");
    return; // Kết thúc hàm mà không trả về giá trị
}
```

### Chi tiết
- Khi một hàm gặp câu lệnh "return", nó sẽ ngay lập tức dừng lại và quay trở lại hàm gọi.
- Nếu hàm không có câu lệnh "return" nhưng đã được định nghĩa với kiểu trả về khác `void`, có thể dẫn đến hành vi không xác định.
- Trong hàm `main`, câu lệnh "return 0;" thường được sử dụng để chỉ ra rằng chương trình đã thực hiện thành công.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng câu lệnh "return":

```c
#include <stdio.h>

int nhân(int x, int y) {
    return x * y; // Trả về tích của x và y
}

int main() {
    int kết_quả = nhân(5, 4);
    printf("Kết quả: %d\n", kết_quả); // In ra: Kết quả: 20
    return 0; // Kết thúc chương trình
}
```

## Giải thích
### Một số lưu ý
- Không nên sử dụng câu lệnh "return" trong các hàm đã được định nghĩa với kiểu trả về `void` mà không theo sau là giá trị.
- Trong một số trường hợp, nếu có nhiều câu lệnh "return" trong một hàm, cần chú ý đến luồng thực thi để tránh nhầm lẫn.
- Khi sử dụng con trỏ, cần đảm bảo rằng giá trị được trả về vẫn còn hợp lệ khi được sử dụng trong hàm gọi.

## Tóm tắt một dòng
Câu lệnh "return" trong ngôn ngữ C được sử dụng để kết thúc hàm và trả về giá trị cho hàm gọi, giữ vai trò quan trọng trong việc kiểm soát luồng chương trình.