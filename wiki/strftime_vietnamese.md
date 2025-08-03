<!--
Meta Description: # Hàm strftime trong ngôn ngữ lập trình C: Định dạng thời gian hiệu quả ## Tóm tắt Hàm `strftime` trong C cho phép người dùng định dạng ngày và giờ th...
Meta Keywords: định, dạng, hàm, strftime, chuỗi
-->

# Hàm strftime trong ngôn ngữ lập trình C: Định dạng thời gian hiệu quả

## Tóm tắt
Hàm `strftime` trong C cho phép người dùng định dạng ngày và giờ thành chuỗi theo yêu cầu, giúp hiển thị thông tin thời gian một cách linh hoạt và dễ hiểu.

## Tài liệu
### Mục đích
Hàm `strftime` được sử dụng để định dạng thời gian từ cấu trúc `tm` thành một chuỗi ký tự theo định dạng mà người dùng chỉ định. Điều này rất hữu ích trong việc trình bày thông tin thời gian cho người dùng hoặc ghi lại thông tin vào nhật ký.

### Cú pháp
```c
size_t strftime(char *str, size_t maxsize, const char *format, const struct tm *timeptr);
```

### Tham số
- **str**: Con trỏ đến mảng ký tự nơi chuỗi kết quả sẽ được lưu trữ.
- **maxsize**: Kích thước tối đa của mảng ký tự `str`.
- **format**: Chuỗi định dạng chứa các ký tự chỉ định cách hiển thị ngày và giờ.
- **timeptr**: Con trỏ đến cấu trúc `tm` chứa thông tin thời gian cần định dạng.

### Giá trị trả về
Hàm trả về số lượng ký tự đã được ghi vào chuỗi `str`, không bao gồm ký tự null kết thúc. Nếu không thể định dạng ngày giờ, hàm sẽ trả về 0.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng hàm `strftime`:

### Ví dụ 1: Định dạng ngày và giờ cơ bản
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    char buffer[80];

    strftime(buffer, sizeof(buffer), "%Y-%m-%d %H:%M:%S", tm_info);
    printf("Thời gian hiện tại: %s\n", buffer);

    return 0;
}
```

### Ví dụ 2: Định dạng chỉ ngày
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    char buffer[80];

    strftime(buffer, sizeof(buffer), "%d-%m-%Y", tm_info);
    printf("Ngày hiện tại: %s\n", buffer);

    return 0;
}
```

## Giải thích
### Các lỗi thường gặp
- **Kích thước mảng không đủ**: Nếu kích thước của mảng `str` nhỏ hơn kích thước chuỗi kết quả, hàm sẽ không thể ghi đủ dữ liệu và có thể dẫn đến lỗi tràn bộ nhớ.
- **Định dạng không hợp lệ**: Nếu chuỗi định dạng không chứa các ký tự hợp lệ, hàm sẽ trả về 0 và không ghi gì vào chuỗi kết quả.
- **Sử dụng con trỏ null**: Đảm bảo rằng con trỏ `timeptr` không phải là null trước khi gọi `strftime`.

### Ghi chú thêm
Hàm `strftime` hỗ trợ nhiều ký tự định dạng khác nhau như `%Y` (năm), `%m` (tháng), `%d` (ngày), `%H` (giờ), `%M` (phút), và `%S` (giây). Bạn có thể tham khảo tài liệu chính thức để biết thêm nhiều ký tự định dạng khác.

## Tóm tắt một dòng
Hàm `strftime` trong C cho phép định dạng thời gian từ cấu trúc `tm` thành chuỗi ký tự theo định dạng tùy chỉnh, cung cấp cách hiển thị ngày giờ linh hoạt và hiệu quả.