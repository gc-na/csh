<!--
Meta Description: # Hàm strrchr trong C: Tìm kiếm ký tự cuối cùng trong chuỗi ## Tóm tắt Hàm `strrchr` trong C được sử dụng để tìm kiếm ký tự cuối cùng xuất hiện trong ...
Meta Keywords: chuỗi, trong, tìm, strrchr, cuối
-->

# Hàm strrchr trong C: Tìm kiếm ký tự cuối cùng trong chuỗi

## Tóm tắt
Hàm `strrchr` trong C được sử dụng để tìm kiếm ký tự cuối cùng xuất hiện trong một chuỗi. Hàm này là một phần của thư viện chuẩn `<string.h>` và rất hữu ích cho việc xử lý chuỗi trong lập trình C.

## Tài liệu
### Mục đích
Hàm `strrchr` tìm vị trí của ký tự cuối cùng trong chuỗi ký tự. Nó trả về con trỏ đến vị trí của ký tự đó trong chuỗi hoặc trả về `NULL` nếu ký tự không tồn tại.

### Cú pháp
```c
char *strrchr(const char *str, int c);
```

### Tham số
- `str`: Con trỏ đến chuỗi ký tự cần tìm kiếm.
- `c`: Ký tự cần tìm, được truyền dưới dạng kiểu `int`, nhưng thực tế là một ký tự.

### Giá trị trả về
Hàm trả về con trỏ đến ký tự cuối cùng tìm thấy trong chuỗi. Nếu ký tự không có trong chuỗi, hàm sẽ trả về `NULL`.

### Lưu ý
- Chuỗi được truyền vào phải là một chuỗi kết thúc bằng ký tự null (`\0`).
- Ký tự cần tìm có thể được chỉ định dưới dạng ký tự đơn hoặc mã ASCII.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng hàm `strrchr`:

### Ví dụ 1: Tìm ký tự cuối cùng
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *result = strrchr(str, 'o');
    
    if (result) {
        printf("Ký tự cuối cùng 'o' trong chuỗi là tại vị trí: %ld\n", result - str);
    } else {
        printf("Ký tự không được tìm thấy.\n");
    }
    
    return 0;
}
```

### Ví dụ 2: Ký tự không tồn tại
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *result = strrchr(str, 'x');
    
    if (result) {
        printf("Ký tự 'x' tìm thấy tại vị trí: %ld\n", result - str);
    } else {
        printf("Ký tự 'x' không tồn tại trong chuỗi.\n");
    }
    
    return 0;
}
```

## Giải thích
- **Cách hoạt động**: `strrchr` quét từ cuối chuỗi về đầu cho đến khi tìm thấy ký tự yêu cầu. Điều này có nghĩa là nó sẽ luôn trả về ký tự cuối cùng nếu có nhiều ký tự giống nhau.
- **Lỗi phổ biến**: Khi sử dụng `strrchr`, một số lập trình viên có thể quên bao gồm thư viện `<string.h>`, dẫn đến lỗi biên dịch. Ngoài ra, việc truyền vào một chuỗi không hợp lệ (không phải là chuỗi null-terminated) cũng có thể dẫn đến hành vi không xác định.

## Tóm tắt ngắn gọn
Hàm `strrchr` trong C giúp tìm kiếm ký tự cuối cùng trong một chuỗi, trả về vị trí của nó hoặc `NULL` nếu không tìm thấy.