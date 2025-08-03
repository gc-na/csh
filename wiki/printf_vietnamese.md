<!--
Meta Description: # Hàm printf trong C: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm tắt Hàm `printf` trong ngôn ngữ lập trình C là một hàm tiêu chuẩn dùng để in ra màn hình các ...
Meta Keywords: printf, hàm, định, các, chuỗi
-->

# Hàm printf trong C: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm tắt
Hàm `printf` trong ngôn ngữ lập trình C là một hàm tiêu chuẩn dùng để in ra màn hình các kiểu dữ liệu khác nhau, từ số nguyên, số thực cho đến chuỗi ký tự.

## Tài liệu
Hàm `printf` được định nghĩa trong thư viện tiêu chuẩn `stdio.h`. Mục đích chính của hàm này là xuất dữ liệu ra thiết bị đầu ra tiêu chuẩn (thường là màn hình). Cú pháp của hàm `printf` như sau:

```c
int printf(const char *format, ...);
```

### Tham số:
- `format`: Chuỗi định dạng (format string) xác định cách thức hiển thị dữ liệu. Trong chuỗi này, bạn có thể sử dụng các ký tự định dạng như `%d`, `%f`, `%s`, v.v. để chỉ định kiểu dữ liệu cần in ra.
- `...`: Danh sách các tham số bổ sung tương ứng với các ký tự định dạng trong chuỗi `format`.

### Trả về:
Hàm `printf` trả về số ký tự đã được in ra (không bao gồm ký tự null kết thúc chuỗi). Nếu có lỗi xảy ra, hàm sẽ trả về giá trị âm.

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng hàm `printf`:

### Ví dụ 1: In số nguyên
```c
#include <stdio.h>

int main() {
    int number = 10;
    printf("Số nguyên là: %d\n", number);
    return 0;
}
```

### Ví dụ 2: In số thực
```c
#include <stdio.h>

int main() {
    float pi = 3.14;
    printf("Giá trị của Pi là: %.2f\n", pi);
    return 0;
}
```

### Ví dụ 3: In chuỗi ký tự
```c
#include <stdio.h>

int main() {
    char name[] = "Nguyễn Văn A";
    printf("Xin chào, %s!\n", name);
    return 0;
}
```

## Giải thích
Khi sử dụng hàm `printf`, có một số điều cần lưu ý:

1. **Tham số không phù hợp**: Đảm bảo rằng số lượng tham số và kiểu dữ liệu của các tham số phải tương ứng với các ký tự định dạng trong chuỗi `format`. Nếu không, sẽ dẫn đến hành vi không mong muốn hoặc lỗi.

2. **Ký tự định dạng**: Các ký tự định dạng phổ biến bao gồm:
   - `%d`: In số nguyên.
   - `%f`: In số thực.
   - `%s`: In chuỗi ký tự.
   - `%c`: In ký tự.
   - `%x`: In số nguyên ở hệ thập lục.

3. **Ký tự đặc biệt**: Để in ra ký tự `%`, bạn cần sử dụng `%%` trong chuỗi định dạng.

4. **Độ chính xác và độ rộng**: Bạn có thể điều chỉnh độ rộng và độ chính xác của các giá trị in ra bằng cách sử dụng cú pháp như `%5d` hoặc `%.2f`.

## Tóm tắt một dòng
Hàm `printf` trong C là công cụ mạnh mẽ để xuất dữ liệu ra màn hình, hỗ trợ nhiều kiểu định dạng khác nhau cho các loại dữ liệu.