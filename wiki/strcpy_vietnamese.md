<!--
Meta Description: # Hàm strcpy trong C: Hướng dẫn và Ví dụ Chi Tiết ## Tóm Tắt Hàm `strcpy` trong ngôn ngữ lập trình C được sử dụng để sao chép một chuỗi ký tự từ một b...
Meta Keywords: chuỗi, đích, strcpy, sao, chép
-->

# Hàm strcpy trong C: Hướng dẫn và Ví dụ Chi Tiết

## Tóm Tắt
Hàm `strcpy` trong ngôn ngữ lập trình C được sử dụng để sao chép một chuỗi ký tự từ một biến nguồn sang một biến đích.

## Tài Liệu
### Mục Đích
Hàm `strcpy` là một phần của thư viện `<string.h>`, cho phép sao chép chuỗi ký tự từ một chuỗi nguồn sang một chuỗi đích. Hàm này rất hữu ích trong việc xử lý chuỗi và quản lý bộ nhớ trong các ứng dụng C.

### Cú Pháp
```c
char *strcpy(char *dest, const char *src);
```

### Tham Số
- `dest`: Con trỏ đến chuỗi đích, nơi mà chuỗi nguồn sẽ được sao chép.
- `src`: Con trỏ đến chuỗi nguồn, chuỗi này sẽ được sao chép vào chuỗi đích.

### Giá Trị Trả Về
Hàm trả về một con trỏ đến chuỗi đích (`dest`).

### Chi Tiết
Hàm `strcpy` sẽ sao chép từng ký tự từ chuỗi `src` vào chuỗi `dest` cho đến khi gặp ký tự null (`'\0'`). Điều này có nghĩa là chuỗi đích cần phải có đủ bộ nhớ để chứa toàn bộ chuỗi nguồn, bao gồm cả ký tự null để đánh dấu kết thúc chuỗi.

## Ví Dụ
### Ví Dụ Cơ Bản
```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[] = "Chào mừng bạn đến với C!";
    char dest[50]; // Đảm bảo đủ bộ nhớ cho chuỗi đích

    strcpy(dest, src); // Sao chép chuỗi

    printf("Chuỗi đích: %s\n", dest); // In ra chuỗi đích
    return 0;
}
```

### Kết Quả
```plaintext
Chuỗi đích: Chào mừng bạn đến với C!
```

## Giải Thích
### Các Lỗi Thường Gặp
1. **Bộ Nhớ Không Đủ**: Nếu chuỗi đích không đủ bộ nhớ để chứa chuỗi nguồn và ký tự null, sẽ dẫn đến hành vi không xác định (undefined behavior).
2. **Sao Chép Chính Mình**: Việc sử dụng `strcpy` với cùng một biến cho cả nguồn và đích (ví dụ: `strcpy(src, src)`) có thể dẫn đến kết quả không mong muốn.

### Ghi Chú Thêm
- Để tránh các lỗi về bộ nhớ, bạn có thể sử dụng `strncpy`, cho phép chỉ định số lượng ký tự cần sao chép.
- Thận trọng với các chuỗi không được kết thúc bằng ký tự null, vì điều này có thể gây ra lỗi khi sử dụng `strcpy`.

## Tóm Tắt Một Dòng
Hàm `strcpy` trong C cho phép sao chép chuỗi ký tự từ chuỗi nguồn sang chuỗi đích, nhưng cần chú ý đến kích thước bộ nhớ để tránh các lỗi không mong muốn.