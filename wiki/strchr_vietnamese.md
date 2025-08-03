<!--
Meta Description: # Hàm strchr trong C: Tìm kiếm ký tự trong chuỗi ## Tóm tắt Hàm `strchr` trong ngôn ngữ lập trình C được sử dụng để tìm kiếm vị trí của một ký tự nhất...
Meta Keywords: chuỗi, trong, tìm, trí, không
-->

# Hàm strchr trong C: Tìm kiếm ký tự trong chuỗi

## Tóm tắt
Hàm `strchr` trong ngôn ngữ lập trình C được sử dụng để tìm kiếm vị trí của một ký tự nhất định trong một chuỗi. Hàm này là một phần của thư viện `<string.h>` và trả về con trỏ tới vị trí đầu tiên của ký tự tìm thấy, hoặc NULL nếu ký tự không tồn tại trong chuỗi.

## Tài liệu
### Mục đích
Hàm `strchr` giúp lập trình viên dễ dàng tìm kiếm ký tự trong chuỗi và có thể được sử dụng trong nhiều tình huống như kiểm tra sự tồn tại của ký tự hoặc phân tách chuỗi.

### Cú pháp
```c
char *strchr(const char *str, int c);
```

### Tham số
- `str`: Con trỏ tới chuỗi cần tìm kiếm.
- `c`: Ký tự (được truyền vào dưới dạng `int`, thường là ký tự ASCII) cần tìm trong chuỗi.

### Giá trị trả về
- Nếu ký tự được tìm thấy, hàm trả về con trỏ tới vị trí đầu tiên của ký tự trong chuỗi.
- Nếu ký tự không tồn tại, hàm trả về NULL.

### Lưu ý
- Ký tự tìm kiếm có thể là một ký tự kết thúc chuỗi (`\0`).
- Kết quả trả về là một con trỏ tới vị trí trong chuỗi, vì vậy bạn có thể tiếp tục thao tác trên chuỗi từ vị trí đó.

## Ví dụ
### Ví dụ 1: Tìm ký tự trong chuỗi
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *result = strchr(str, 'o');

    if (result != NULL) {
        printf("Ký tự 'o' được tìm thấy tại vị trí: %ld\n", result - str);
    } else {
        printf("Ký tự 'o' không tồn tại trong chuỗi.\n");
    }

    return 0;
}
```

### Ví dụ 2: Tìm ký tự kết thúc chuỗi
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *result = strchr(str, '\0');

    if (result != NULL) {
        printf("Ký tự kết thúc chuỗi được tìm thấy tại vị trí: %ld\n", result - str);
    }

    return 0;
}
```

## Giải thích
### Những cạm bẫy thường gặp
- **Không kiểm tra NULL**: Khi tìm kiếm ký tự, nếu không kiểm tra giá trị trả về có phải là NULL hay không, bạn có thể gây ra lỗi chương trình khi cố gắng truy cập vào vị trí không hợp lệ.
- **Ký tự không có trong chuỗi**: Nếu ký tự không tồn tại trong chuỗi, chắc chắn rằng logic của bạn xử lý tình huống này một cách thích hợp để tránh lỗi.
- **Sử dụng con trỏ sau khi chuỗi đã bị giải phóng**: Luôn đảm bảo rằng chuỗi mà bạn đang làm việc với vẫn còn hợp lệ trong bộ nhớ khi sử dụng con trỏ trả về từ `strchr`.

## Tóm tắt một dòng
Hàm `strchr` trong C cho phép tìm kiếm vị trí của một ký tự trong chuỗi và trả về con trỏ tới vị trí đó hoặc NULL nếu không tìm thấy.