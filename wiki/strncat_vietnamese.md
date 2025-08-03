<!--
Meta Description: # Hàm strncat trong C: Gộp chuỗi với độ dài giới hạn ## Tóm tắt Hàm `strncat` trong ngôn ngữ lập trình C được sử dụng để nối một chuỗi đến một chuỗi k...
Meta Keywords: chuỗi, nối, dest, strncat, src
-->

# Hàm strncat trong C: Gộp chuỗi với độ dài giới hạn

## Tóm tắt
Hàm `strncat` trong ngôn ngữ lập trình C được sử dụng để nối một chuỗi đến một chuỗi khác với một độ dài giới hạn, giúp tránh tràn bộ nhớ.

## Tài liệu
Hàm `strncat` thuộc thư viện `<string.h>` và có cú pháp như sau:

```c
char *strncat(char *dest, const char *src, size_t n);
```

### Mục đích
Hàm `strncat` được sử dụng để nối chuỗi `src` vào chuỗi `dest` nhưng chỉ nối tối đa `n` ký tự từ `src`. Điều này giúp bảo vệ bộ nhớ và ngăn ngừa lỗi tràn bộ nhớ.

### Tham số
- `dest`: Con trỏ đến chuỗi đích mà bạn muốn nối vào. Chuỗi này phải đủ lớn để chứa kết quả.
- `src`: Con trỏ đến chuỗi nguồn mà bạn muốn nối vào chuỗi đích.
- `n`: Số ký tự tối đa từ `src` mà bạn muốn nối vào `dest`.

### Giá trị trả về
Hàm `strncat` trả về con trỏ đến chuỗi `dest`.

### Chi tiết
- `strncat` sẽ tự động thêm ký tự null (`'\0'`) vào cuối chuỗi đích sau khi thực hiện việc nối.
- Nếu chiều dài của `src` nhỏ hơn `n`, toàn bộ chuỗi `src` sẽ được nối vào `dest`.
- Nếu chiều dài của `src` lớn hơn hoặc bằng `n`, chỉ `n` ký tự đầu tiên của `src` sẽ được nối vào `dest`.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng hàm `strncat`:

### Ví dụ 1: Nối chuỗi cơ bản
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20] = "Xin chao, ";
    char src[] = "the gioi!";
    
    strncat(dest, src, 6); // Chỉ nối 6 ký tự
    printf("%s\n", dest); // Kết quả: Xin chao, the gi
    return 0;
}
```

### Ví dụ 2: Nối toàn bộ chuỗi nguồn
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20] = "Chao ";
    char src[] = "cac ban!";
    
    strncat(dest, src, 10); // Chỉ nối tối đa 10 ký tự
    printf("%s\n", dest); // Kết quả: Chao cac ban!
    return 0;
}
```

## Giải thích
- **Lỗi phổ biến**: Một trong những lỗi phổ biến khi sử dụng `strncat` là không đảm bảo rằng chuỗi `dest` có đủ bộ nhớ để chứa kết quả sau khi nối. Điều này có thể dẫn đến tràn bộ nhớ.
- **Ký tự null**: Luôn nhớ rằng `strncat` sẽ thêm ký tự null (`'\0'`) vào cuối chuỗi `dest`. Nếu không có đủ không gian để chứa ký tự null, bạn vẫn có thể gặp phải lỗi tràn bộ nhớ.
- **Khả năng bảo mật**: Sử dụng `n` giúp bảo vệ chương trình khỏi các tấn công tràn bộ nhớ, nhưng vẫn cần phải kiểm tra kích thước của các chuỗi.

## Tóm tắt một dòng
Hàm `strncat` trong C cho phép nối chuỗi với độ dài giới hạn, giúp tránh các lỗi tràn bộ nhớ.