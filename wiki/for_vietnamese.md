<!--
Meta Description: # C: Câu Lệnh "for" - Cấu Trúc Lặp Trong Ngôn Ngữ Lập Trình C ## Tóm tắt Câu lệnh "for" trong ngôn ngữ lập trình C là một cấu trúc lặp mạnh mẽ, cho ph...
Meta Keywords: lặp, lệnh, một, câu, điều
-->

# C: Câu Lệnh "for" - Cấu Trúc Lặp Trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Câu lệnh "for" trong ngôn ngữ lập trình C là một cấu trúc lặp mạnh mẽ, cho phép lập trình viên thực hiện một khối mã lệnh nhiều lần với điều kiện được xác định trước. Đây là một trong những cách phổ biến nhất để xử lý các vòng lặp trong C.

## Tài liệu
Câu lệnh "for" được sử dụng để lặp qua một đoạn mã với ba phần chính: khởi tạo, điều kiện và bước nhảy. Cấu trúc tổng quát của câu lệnh "for" như sau:

```c
for (khởi_tạo; điều_kiện; bước_nhảy) {
    // Mã lệnh cần thực thi
}
```

### Mô tả các thành phần:
- **Khởi Tạo**: Đây là nơi bạn thiết lập biến đếm ban đầu. Nó chỉ được thực thi một lần khi vòng lặp bắt đầu.
- **Điều Kiện**: Đây là biểu thức điều kiện mà vòng lặp sẽ kiểm tra trước mỗi lần lặp. Nếu điều kiện đúng (khác 0), vòng lặp sẽ tiếp tục; nếu sai (bằng 0), vòng lặp sẽ dừng lại.
- **Bước Nhảy**: Đây là biểu thức được thực thi sau mỗi lần lặp, thường dùng để cập nhật biến đếm.

### Ví dụ:
Dưới đây là một số ví dụ cơ bản về cách sử dụng câu lệnh "for" trong C:

#### Ví dụ 1: In các số từ 1 đến 5
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {
        printf("%d\n", i);
    }
    return 0;
}
```

#### Ví dụ 2: Tính tổng các số từ 1 đến 10
```c
#include <stdio.h>

int main() {
    int sum = 0;
    for (int i = 1; i <= 10; i++) {
        sum += i;
    }
    printf("Tổng từ 1 đến 10 là: %d\n", sum);
    return 0;
}
```

## Giải thích
Khi sử dụng câu lệnh "for", có một số điều cần lưu ý để tránh các lỗi phổ biến:
- **Vòng lặp vô hạn**: Nếu điều kiện không bao giờ trở thành sai, vòng lặp sẽ không bao giờ dừng lại. Hãy chắc chắn rằng biến đếm được cập nhật đúng cách trong bước nhảy.
- **Khởi tạo sai**: Nếu biến khởi tạo không đúng kiểu hoặc không được khởi tạo, có thể dẫn đến hành vi không mong muốn.
- **Cú pháp**: Đảm bảo rằng bạn sử dụng dấu chấm phẩy (;) đúng cách để phân tách các phần của câu lệnh "for".

## Tóm tắt một dòng
Câu lệnh "for" trong C là một công cụ lặp linh hoạt cho phép thực thi mã lệnh nhiều lần dựa trên điều kiện được chỉ định.