<!--
Meta Description: # Hàm `strncpy` trong C: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể ## Tóm tắt Hàm `strncpy` trong ngôn ngữ lập trình C được sử dụng để sao chép một chuỗi ký ...
Meta Keywords: chuỗi, đích, dest, strncpy, sao
-->

# Hàm `strncpy` trong C: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể

## Tóm tắt
Hàm `strncpy` trong ngôn ngữ lập trình C được sử dụng để sao chép một chuỗi ký tự từ nguồn đến đích với khả năng kiểm soát số lượng ký tự sao chép, giúp người lập trình tránh lỗi tràn bộ nhớ.

## Tài liệu
### Mục đích
Hàm `strncpy` được thiết kế để sao chép tối đa `n` ký tự từ chuỗi nguồn (`src`) vào chuỗi đích (`dest`). Nó là một phần của thư viện `<string.h>`.

### Cú pháp
```c
char *strncpy(char *dest, const char *src, size_t n);
```

### Tham số
- `dest`: Con trỏ đến chuỗi đích nơi dữ liệu sẽ được sao chép.
- `src`: Con trỏ đến chuỗi nguồn từ đó dữ liệu sẽ được sao chép.
- `n`: Số lượng ký tự tối đa cần sao chép từ chuỗi nguồn.

### Giá trị trả về
Hàm trả về con trỏ đến chuỗi đích (`dest`).

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng hàm `strncpy`:

### Ví dụ 1: Sao chép chuỗi cơ bản
```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[] = "Hello, World!";
    char dest[20];

    strncpy(dest, src, 5);
    dest[5] = '\0'; // Thêm ký tự kết thúc chuỗi

    printf("Chuỗi đích: %s\n", dest); // Kết quả: Hello
    return 0;
}
```

### Ví dụ 2: Khi chuỗi nguồn ngắn hơn số ký tự cần sao chép
```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[] = "Hi";
    char dest[20];

    strncpy(dest, src, 10);
    dest[10] = '\0'; // Đảm bảo chuỗi kết thúc đúng

    printf("Chuỗi đích: %s\n", dest); // Kết quả: Hi
    return 0;
}
```

## Giải thích
### Những cạm bẫy phổ biến
1. **Thiếu ký tự kết thúc chuỗi**: Nếu số ký tự sao chép nhỏ hơn `n` và chuỗi nguồn không đủ dài, chuỗi đích sẽ không được tự động kết thúc bằng ký tự null (`\0`). Điều này có thể dẫn đến lỗi khi sử dụng chuỗi sau này.
2. **Tràn bộ nhớ**: Nếu không đảm bảo rằng chuỗi đích đủ lớn để chứa các ký tự sao chép, có thể dẫn đến tràn bộ nhớ. Luôn kiểm tra kích thước của chuỗi đích trước khi sử dụng `strncpy`.

### Lưu ý thêm
- Hàm `strncpy` không đảm bảo rằng chuỗi đích luôn kết thúc bằng ký tự null, nên người lập trình cần phải thêm ký tự null một cách thủ công nếu cần.
- Sử dụng `strncpy` thay vì `strcpy` là một phương pháp an toàn hơn để tránh lỗi tràn bộ nhớ, nhưng cần phải cẩn thận với việc kết thúc chuỗi.

## Tóm tắt một dòng
Hàm `strncpy` trong C là công cụ hữu ích để sao chép một số lượng ký tự nhất định từ chuỗi nguồn sang chuỗi đích, nhưng cần cẩn trọng để đảm bảo chuỗi kết thúc đúng cách và tránh tràn bộ nhớ.