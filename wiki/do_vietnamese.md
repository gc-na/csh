<!--
Meta Description: # Cấu Trúc Lệnh "do" Trong Ngôn Ngữ Lập Trình C ## Tóm Tắt Lệnh "do" trong ngôn ngữ lập trình C được sử dụng để tạo ra cấu trúc lặp "do...while", cho ...
Meta Keywords: lệnh, điều, kiện, lặp, một
-->

# Cấu Trúc Lệnh "do" Trong Ngôn Ngữ Lập Trình C

## Tóm Tắt
Lệnh "do" trong ngôn ngữ lập trình C được sử dụng để tạo ra cấu trúc lặp "do...while", cho phép thực hiện một khối lệnh ít nhất một lần trước khi kiểm tra điều kiện lặp.

## Tài Liệu
### Mục Đích
Cấu trúc lặp "do...while" cho phép lập trình viên lặp qua một khối lệnh cho đến khi điều kiện xác định là sai. Đây là một cách hữu ích để đảm bảo rằng một khối mã được thực thi ít nhất một lần, trước khi vào vòng lặp.

### Cách Sử Dụng
Cú pháp cơ bản của lệnh "do" trong C như sau:

```c
do {
    // Khối lệnh cần thực thi
} while (điều kiện);
```

### Chi Tiết
- **do**: Từ khóa để bắt đầu khối lệnh.
- **{ }**: Đánh dấu khối lệnh sẽ được thực thi.
- **while (điều kiện)**: Kiểm tra điều kiện. Nếu điều kiện đúng (khác 0), vòng lặp sẽ tiếp tục thực thi.

Điều kiện trong phần "while" có thể là bất kỳ biểu thức logic nào. Khi điều kiện sai (bằng 0), vòng lặp sẽ dừng lại.

## Ví Dụ
### Ví Dụ Cơ Bản
Dưới đây là một ví dụ đơn giản về cách sử dụng lệnh "do...while":

```c
#include <stdio.h>

int main() {
    int i = 0;

    do {
        printf("Giá trị của i: %d\n", i);
        i++;
    } while (i < 5);

    return 0;
}
```

**Kết quả đầu ra:**
```
Giá trị của i: 0
Giá trị của i: 1
Giá trị của i: 2
Giá trị của i: 3
Giá trị của i: 4
```

Trong ví dụ này, khối lệnh in giá trị của `i` ra màn hình ít nhất một lần và tiếp tục cho đến khi `i` đạt giá trị 5.

## Giải Thích
### Những Lưu Ý Chung
- **Ít Nhất Một Lần Thực Thi**: Khác với vòng lặp "while", vòng lặp "do...while" sẽ luôn thực thi khối lệnh ít nhất một lần.
- **Biểu Thức Điều Kiện**: Đảm bảo rằng biểu thức điều kiện không gây ra lỗi khi thực thi. Ví dụ, nếu điều kiện sử dụng biến chưa được khởi tạo, có thể dẫn đến hành vi không mong muốn.
- **Kết Thúc Vòng Lặp**: Luôn kiểm tra đầu vào hoặc điều kiện để tránh việc lặp vô hạn.

## Tóm Tắt Một Dòng
Lệnh "do" trong C được sử dụng để tạo vòng lặp "do...while", cho phép thực thi khối lệnh ít nhất một lần trước khi kiểm tra điều kiện.