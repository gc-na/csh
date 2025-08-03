<!--
Meta Description: # Hàm putchar trong C: Cách sử dụng và ví dụ ## Tóm tắt Hàm `putchar` trong ngôn ngữ lập trình C được sử dụng để xuất một ký tự đơn ra màn hình. Đây l...
Meta Keywords: putchar, hàm, một, int, dụng
-->

# Hàm putchar trong C: Cách sử dụng và ví dụ

## Tóm tắt
Hàm `putchar` trong ngôn ngữ lập trình C được sử dụng để xuất một ký tự đơn ra màn hình. Đây là một hàm đơn giản nhưng hữu ích trong việc hiển thị thông tin cho người dùng.

## Tài liệu
### Mục đích
Hàm `putchar` thuộc thư viện `<stdio.h>`, và nó được dùng để in một ký tự đến standard output (thường là màn hình).

### Cú pháp
```c
int putchar(int character);
```

### Tham số
- `character`: Ký tự cần được in ra, được truyền dưới dạng kiểu `int`. Ký tự này có thể là một ký tự ASCII (từ 0 đến 255).

### Giá trị trả về
- Hàm trả về ký tự đã được in ra dưới dạng `unsigned char` cast về kiểu `int`.
- Nếu có lỗi xảy ra, hàm trả về `EOF` (End Of File).

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng hàm `putchar`.

### Ví dụ 1: In một ký tự đơn
```c
#include <stdio.h>

int main() {
    putchar('A');
    return 0;
}
```

### Ví dụ 2: In nhiều ký tự
```c
#include <stdio.h>

int main() {
    putchar('H');
    putchar('e');
    putchar('l');
    putchar('l');
    putchar('o');
    putchar('\n'); // In xuống dòng
    return 0;
}
```

### Ví dụ 3: Sử dụng trong vòng lặp
```c
#include <stdio.h>

int main() {
    for (char c = 'A'; c <= 'Z'; c++) {
        putchar(c);
    }
    putchar('\n'); // In xuống dòng
    return 0;
}
```

## Giải thích
### Những điều cần lưu ý
- Hàm `putchar` chỉ có thể in một ký tự tại một thời điểm. Nếu bạn cần in nhiều ký tự, bạn sẽ cần gọi hàm này nhiều lần.
- Để in ký tự đặc biệt như xuống dòng (`'\n'`) hoặc tab (`'\t'`), bạn cần sử dụng ký tự escape tương ứng.
- Đảm bảo bạn đã bao gồm thư viện `<stdio.h>` trước khi sử dụng hàm này, nếu không sẽ gặp lỗi biên dịch.

### Lỗi thường gặp
- Quên bao gồm thư viện `<stdio.h>`, dẫn đến lỗi không xác định hàm `putchar`.
- Gửi giá trị không phải là ký tự (như chuỗi hay số nguyên lớn hơn 255) có thể gây ra hành vi không mong muốn.

## Tóm tắt ngắn gọn
Hàm `putchar` là công cụ đơn giản nhưng mạnh mẽ để in ký tự ra màn hình trong ngôn ngữ lập trình C.