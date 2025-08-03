<!--
Meta Description: # Hàm strlen trong ngôn ngữ lập trình C: Hướng dẫn chi tiết ## Tóm tắt Hàm `strlen` trong ngôn ngữ C được sử dụng để tính toán độ dài của một chuỗi ký...
Meta Keywords: chuỗi, hàm, strlen, dài, một
-->

# Hàm strlen trong ngôn ngữ lập trình C: Hướng dẫn chi tiết

## Tóm tắt
Hàm `strlen` trong ngôn ngữ C được sử dụng để tính toán độ dài của một chuỗi ký tự, không bao gồm ký tự null (`\0`) ở cuối.

## Tài liệu
### Mục đích
Hàm `strlen` cung cấp một cách đơn giản để xác định số lượng ký tự trong một chuỗi. Điều này rất hữu ích trong việc xử lý chuỗi, như khi cần xác định độ dài để phân bổ bộ nhớ hoặc khi cần lặp qua các ký tự trong chuỗi.

### Cú pháp
```c
#include <string.h>

size_t strlen(const char *str);
```

### Tham số
- `str`: Con trỏ đến chuỗi ký tự mà bạn muốn tính độ dài.

### Giá trị trả về
Hàm trả về một giá trị kiểu `size_t`, đại diện cho số lượng ký tự trong chuỗi, không bao gồm ký tự null ở cuối.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng hàm `strlen`:

### Ví dụ 1: Tính độ dài của một chuỗi
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *myString = "Hello, World!";
    size_t length = strlen(myString);
    printf("Độ dài của chuỗi là: %zu\n", length);
    return 0;
}
```

### Ví dụ 2: Sử dụng với chuỗi rỗng
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *emptyString = "";
    size_t length = strlen(emptyString);
    printf("Độ dài của chuỗi rỗng là: %zu\n", length);
    return 0;
}
```

## Giải thích
### Những điều cần lưu ý
- **Ký tự Null**: Hàm `strlen` không tính ký tự null (`\0`). Điều này có nghĩa là nếu bạn có một chuỗi nhiều ký tự, bạn cần phải nhớ rằng ký tự null không được tính trong độ dài.
- **Chuỗi không hợp lệ**: Nếu bạn truyền một con trỏ không hợp lệ (null hoặc không trỏ đến một vùng nhớ hợp lệ), hàm sẽ gây ra hành vi không xác định (undefined behavior) và có thể dẫn đến lỗi chương trình.
- **Hiệu suất**: Hàm `strlen` có độ phức tạp O(n), trong đó n là độ dài của chuỗi. Điều này có nghĩa là hàm sẽ cần phải duyệt qua từng ký tự để tính toán độ dài.

## Tóm tắt một dòng
Hàm `strlen` trong C là công cụ hữu ích để tính toán độ dài của chuỗi ký tự, không bao gồm ký tự null ở cuối.