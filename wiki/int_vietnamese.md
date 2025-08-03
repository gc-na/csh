<!--
Meta Description: # Kiểu Dữ Liệu int trong Ngôn Ngữ Lập Trình C ## Tóm tắt Kiểu dữ liệu `int` trong ngôn ngữ lập trình C là kiểu số nguyên, được sử dụng phổ biến để lưu...
Meta Keywords: int, kiểu, trong, của, liệu
-->

# Kiểu Dữ Liệu int trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Kiểu dữ liệu `int` trong ngôn ngữ lập trình C là kiểu số nguyên, được sử dụng phổ biến để lưu trữ các giá trị số nguyên trong các chương trình. Đây là một trong những kiểu dữ liệu cơ bản nhất mà lập trình viên cần nắm vững.

## Tài liệu
### Mục đích
Kiểu dữ liệu `int` được sử dụng để lưu trữ các giá trị số nguyên trong chương trình C. Nó cho phép lập trình viên thực hiện các phép toán số học cơ bản như cộng, trừ, nhân và chia.

### Cách sử dụng
Để khai báo một biến kiểu `int`, bạn có thể sử dụng cú pháp sau:
```c
int ten_bien;
```
Bạn có thể khởi tạo biến này với một giá trị cụ thể như sau:
```c
int so = 10;
```
### Chi tiết
- Kiểu `int` có thể lưu trữ số nguyên dương và âm.
- Kích thước của kiểu `int` phụ thuộc vào hệ thống (thường là 2 hoặc 4 byte).
- Giá trị tối đa và tối thiểu của kiểu `int` có thể được xác định thông qua các hằng số trong thư viện `<limits.h>`: `INT_MAX` và `INT_MIN`.

## Ví dụ
```c
#include <stdio.h>
#include <limits.h>

int main() {
    int a = 5;
    int b = -3;
    int sum = a + b;

    printf("Tổng của %d và %d là: %d\n", a, b, sum);
    printf("Giá trị tối đa của int: %d\n", INT_MAX);
    printf("Giá trị tối thiểu của int: %d\n", INT_MIN);

    return 0;
}
```

## Giải thích
- **Tránh sử dụng số quá lớn**: Khi sử dụng kiểu `int`, hãy đảm bảo rằng giá trị bạn lưu trữ không vượt quá giới hạn của kiểu dữ liệu. Nếu vượt quá, có thể xảy ra hiện tượng "tràn số" (overflow).
- **Kích thước biến**: Kích thước của biến `int` có thể thay đổi tùy theo hệ điều hành và kiến trúc máy tính. Do đó, hãy kiểm tra kích thước của kiểu `int` trong môi trường phát triển của bạn nếu cần.
- **Sử dụng đúng ngữ cảnh**: Hãy chọn kiểu dữ liệu phù hợp cho các phép toán cần thiết. Đối với số thực, hãy xem xét sử dụng kiểu `float` hoặc `double`.

## Tóm tắt một dòng
Kiểu dữ liệu `int` trong ngôn ngữ lập trình C là kiểu số nguyên cho phép lưu trữ và thao tác với các giá trị số nguyên trong các chương trình.