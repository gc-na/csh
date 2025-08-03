<!--
Meta Description: # Hàm strcmp trong C: So sánh Chuỗi Một Cách Hiệu Quả ## Tóm tắt Hàm `strcmp` trong ngôn ngữ lập trình C được sử dụng để so sánh hai chuỗi ký tự, giúp...
Meta Keywords: hàm, strcmp, sánh, str1, chuỗi
-->

# Hàm strcmp trong C: So sánh Chuỗi Một Cách Hiệu Quả

## Tóm tắt
Hàm `strcmp` trong ngôn ngữ lập trình C được sử dụng để so sánh hai chuỗi ký tự, giúp xác định thứ tự từ điển của chúng.

## Tài liệu
Hàm `strcmp` có cú pháp như sau:

```c
int strcmp(const char *str1, const char *str2);
```

### Mục đích
Hàm `strcmp` so sánh hai chuỗi ký tự `str1` và `str2`. Nó trả về một giá trị nguyên cho biết kết quả so sánh:

- Nếu `str1` nhỏ hơn `str2`, hàm trả về một giá trị nhỏ hơn 0.
- Nếu `str1` bằng `str2`, hàm trả về 0.
- Nếu `str1` lớn hơn `str2`, hàm trả về một giá trị lớn hơn 0.

### Sử dụng
Hàm `strcmp` thường được sử dụng trong các tình huống như:

- Kiểm tra sự bằng nhau của hai chuỗi.
- Sắp xếp danh sách chuỗi theo thứ tự từ điển.
- Thực hiện các phép so sánh trong điều kiện.

### Chi tiết
- Hàm `strcmp` là một phần của thư viện `<string.h>`, vì vậy cần phải bao gồm thư viện này trong chương trình.
- So sánh được thực hiện theo từng ký tự, cho đến khi gặp ký tự khác hoặc kết thúc chuỗi.
- Hàm này so sánh theo mã ASCII, vì vậy "A" sẽ được coi là nhỏ hơn "a".

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng hàm `strcmp`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "World";
    char str3[] = "Hello";

    int result1 = strcmp(str1, str2);
    int result2 = strcmp(str1, str3);

    printf("Kết quả so sánh str1 và str2: %d\n", result1); // Kết quả sẽ nhỏ hơn 0
    printf("Kết quả so sánh str1 và str3: %d\n", result2); // Kết quả sẽ bằng 0

    return 0;
}
```

## Giải thích
Khi sử dụng `strcmp`, cần lưu ý một số vấn đề sau:

- **Ký tự đặc biệt**: Chú ý đến các ký tự đặc biệt và khoảng trắng, vì chúng có thể ảnh hưởng đến kết quả so sánh.
- **Chữ hoa và chữ thường**: Hàm `strcmp` phân biệt chữ hoa và chữ thường. Ví dụ, "abc" khác với "ABC".
- **Ký tự null**: Đảm bảo chuỗi được kết thúc bằng ký tự null (`\0`) để tránh lỗi khi so sánh.

## Tóm tắt một dòng
Hàm `strcmp` trong C là công cụ hiệu quả để so sánh hai chuỗi ký tự và xác định thứ tự từ điển của chúng.