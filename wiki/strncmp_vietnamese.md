<!--
Meta Description: # Hàm strncmp trong ngôn ngữ lập trình C ## Tóm tắt Hàm `strncmp` trong C là một hàm dùng để so sánh một số lượng ký tự nhất định của hai chuỗi. Hàm n...
Meta Keywords: chuỗi, một, hàm, sánh, trong
-->

# Hàm strncmp trong ngôn ngữ lập trình C

## Tóm tắt
Hàm `strncmp` trong C là một hàm dùng để so sánh một số lượng ký tự nhất định của hai chuỗi. Hàm này rất hữu ích trong việc kiểm tra các chuỗi mà không cần phải so sánh toàn bộ chuỗi, đặc biệt khi chỉ cần so sánh một phần của chúng.

## Tài liệu
### Mục đích
Hàm `strncmp` được sử dụng để so sánh hai chuỗi ký tự cho đến một số lượng ký tự nhất định, giúp bạn xác định xem chúng có giống nhau hay không.

### Cú pháp
```c
int strncmp(const char *str1, const char *str2, size_t n);
```

### Tham số
- `str1`: Con trỏ đến chuỗi ký tự đầu tiên.
- `str2`: Con trỏ đến chuỗi ký tự thứ hai.
- `n`: Số ký tự tối đa để so sánh.

### Trả về
Hàm trả về:
- Một số dương nếu `str1` lớn hơn `str2`.
- Một số âm nếu `str1` nhỏ hơn `str2`.
- 0 nếu hai chuỗi giống nhau trong n ký tự đầu.

## Ví dụ
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hello, World!";
    const char *str2 = "Hello, C!";
    
    int result = strncmp(str1, str2, 5);
    if (result == 0) {
        printf("Hai chuỗi giống nhau trong 5 ký tự đầu.\n");
    } else {
        printf("Hai chuỗi khác nhau trong 5 ký tự đầu.\n");
    }
    
    return 0;
}
```

## Giải thích
Khi sử dụng `strncmp`, bạn cần lưu ý một số điều sau:
- Nếu một trong các chuỗi ngắn hơn n ký tự, hàm sẽ so sánh cho đến khi hết chuỗi, có thể dẫn đến kết quả không như mong đợi.
- Hàm không tự động thêm ký tự null (`'\0'`) vào cuối chuỗi, vì vậy cần đảm bảo rằng các chuỗi đã được kết thúc đúng cách.
- Việc so sánh các chuỗi không nhạy cảm với chữ hoa chữ thường. Để so sánh không phân biệt chữ hoa chữ thường, bạn có thể sử dụng hàm `strncasecmp`.

## Tóm tắt một câu
Hàm `strncmp` trong C cho phép bạn so sánh một số ký tự nhất định của hai chuỗi ký tự một cách hiệu quả.