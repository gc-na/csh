<!--
Meta Description: # Hướng Dẫn Sử Dụng Hàm scanf trong Ngôn Ngữ Lập Trình C ## Tóm Tắt Hàm `scanf` trong C là một hàm chuẩn dùng để đọc đầu vào từ bàn phím, cho phép ngư...
Meta Keywords: đọc, scanf, liệu, định, hàm
-->

# Hướng Dẫn Sử Dụng Hàm scanf trong Ngôn Ngữ Lập Trình C

## Tóm Tắt
Hàm `scanf` trong C là một hàm chuẩn dùng để đọc đầu vào từ bàn phím, cho phép người dùng nhập dữ liệu vào chương trình. Nó hỗ trợ nhiều loại dữ liệu khác nhau và có khả năng kiểm tra định dạng đầu vào.

## Tài Liệu
### Mục Đích
Hàm `scanf` được sử dụng để đọc dữ liệu từ đầu vào tiêu chuẩn (thường là bàn phím) và lưu trữ giá trị vào các biến theo định dạng đã chỉ định.

### Cú Pháp
```c
int scanf(const char *format, ...);
```

- `format`: Chuỗi định dạng chỉ định kiểu dữ liệu và cách mà dữ liệu sẽ được đọc.
- `...`: Một hoặc nhiều biến con trỏ để lưu trữ giá trị đã đọc.

### Các Định Dạng Thông Dụng
- `%d`: Đọc số nguyên.
- `%f`: Đọc số thực.
- `%c`: Đọc ký tự.
- `%s`: Đọc chuỗi ký tự.

### Trả Về
Hàm `scanf` trả về số lượng biến thành công được gán giá trị. Nếu không có giá trị nào được gán, nó trả về `EOF`.

## Ví Dụ
### Ví Dụ 1: Đọc Số Nguyên
```c
#include <stdio.h>

int main() {
    int num;
    printf("Nhập một số nguyên: ");
    scanf("%d", &num);
    printf("Bạn đã nhập: %d\n", num);
    return 0;
}
```

### Ví Dụ 2: Đọc Chuỗi
```c
#include <stdio.h>

int main() {
    char name[50];
    printf("Nhập tên của bạn: ");
    scanf("%s", name);
    printf("Xin chào, %s!\n", name);
    return 0;
}
```

### Ví Dụ 3: Đọc Nhiều Dữ Liệu
```c
#include <stdio.h>

int main() {
    int age;
    float height;
    printf("Nhập tuổi và chiều cao (tuổi chiều cao): ");
    scanf("%d %f", &age, &height);
    printf("Tuổi: %d, Chiều cao: %.2f\n", age, height);
    return 0;
}
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Quên Địa Chỉ Biến**: Cần phải sử dụng toán tử `&` trước biến khi sử dụng với `%d`, `%f` (trừ `%s` vì nó đã là con trỏ).
- **Đọc Ký Tự Không Ghi Nhớ**: Hàm `scanf` không tự động xóa ký tự newline (`\n`) trong bộ đệm, có thể gây ra vấn đề khi đọc các kiểu dữ liệu khác sau đó.
- **Giới Hạn Độ Dài Chuỗi**: Khi đọc chuỗi, nên giới hạn kích thước để tránh lỗi tràn bộ nhớ, ví dụ: `scanf("%49s", name);` với kích thước mảng `name` là 50.

## Tóm Tắt Một Dòng
Hàm `scanf` trong C cho phép người dùng nhập dữ liệu từ bàn phím và lưu trữ vào biến theo định dạng đã chỉ định.