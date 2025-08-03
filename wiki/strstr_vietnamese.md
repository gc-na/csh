<!--
Meta Description: # Hàm strstr trong C: Tìm kiếm chuỗi con ## Tóm tắt Hàm `strstr` trong ngôn ngữ lập trình C được sử dụng để tìm kiếm một chuỗi con trong một chuỗi lớn...
Meta Keywords: chuỗi, con, tìm, needle, hàm
-->

# Hàm strstr trong C: Tìm kiếm chuỗi con

## Tóm tắt
Hàm `strstr` trong ngôn ngữ lập trình C được sử dụng để tìm kiếm một chuỗi con trong một chuỗi lớn hơn. Hàm này rất hữu ích khi bạn cần xác định vị trí xuất hiện đầu tiên của một chuỗi trong một chuỗi khác.

## Tài liệu
Hàm `strstr` có cú pháp như sau:

```c
char *strstr(const char *haystack, const char *needle);
```

### Mục đích
Hàm `strstr` tìm kiếm chuỗi con (`needle`) trong chuỗi lớn hơn (`haystack`). Nếu tìm thấy chuỗi con, hàm sẽ trả về con trỏ đến vị trí bắt đầu của chuỗi con trong chuỗi lớn. Nếu không tìm thấy, hàm sẽ trả về `NULL`.

### Tham số
- `haystack`: Chuỗi lớn hơn nơi bạn muốn tìm kiếm.
- `needle`: Chuỗi con mà bạn muốn tìm.

### Giá trị trả về
- Trả về con trỏ đến vị trí bắt đầu của chuỗi con trong chuỗi lớn.
- Trả về `NULL` nếu không tìm thấy chuỗi con.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng hàm `strstr`:

### Ví dụ 1: Tìm kiếm chuỗi con
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Xin chào, thế giới!";
    const char *needle = "thế giới";
    
    char *result = strstr(haystack, needle);
    if (result) {
        printf("Chuỗi con '%s' được tìm thấy tại vị trí: %ld\n", needle, result - haystack);
    } else {
        printf("Không tìm thấy chuỗi con '%s'\n", needle);
    }
    return 0;
}
```

### Ví dụ 2: Không tìm thấy chuỗi con
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Xin chào, thế giới!";
    const char *needle = "C++";
    
    char *result = strstr(haystack, needle);
    if (result) {
        printf("Chuỗi con '%s' được tìm thấy tại vị trí: %ld\n", needle, result - haystack);
    } else {
        printf("Không tìm thấy chuỗi con '%s'\n", needle);
    }
    return 0;
}
```

## Giải thích
Một số điều cần lưu ý khi sử dụng hàm `strstr`:

- **Phân biệt chữ hoa chữ thường**: Hàm `strstr` phân biệt giữa chữ hoa và chữ thường. Ví dụ, chuỗi "Thế Giới" sẽ không được tìm thấy nếu bạn tìm kiếm "thế giới".
- **Chuỗi con rỗng**: Nếu `needle` là một chuỗi rỗng, hàm `strstr` sẽ trả về con trỏ đến đầu chuỗi `haystack`.
- **Kết thúc chuỗi**: Đảm bảo chuỗi `haystack` và `needle` được kết thúc bằng ký tự null (`'\0'`) để tránh lỗi truy cập bộ nhớ.

## Tóm tắt một dòng
Hàm `strstr` trong C cho phép bạn tìm kiếm chuỗi con trong một chuỗi lớn, trả về vị trí xuất hiện đầu tiên hoặc `NULL` nếu không tìm thấy.