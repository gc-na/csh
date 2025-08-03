<!--
Meta Description: # Tìm Hiểu Về Macro __TIME__ Trong Ngôn Ngữ Lập Trình C ## Tóm Tắt Macro `__TIME__` trong ngôn ngữ lập trình C là một tính năng cho phép lập trình viê...
Meta Keywords: trình, biên, dịch, __time__, thời
-->

# Tìm Hiểu Về Macro __TIME__ Trong Ngôn Ngữ Lập Trình C

## Tóm Tắt
Macro `__TIME__` trong ngôn ngữ lập trình C là một tính năng cho phép lập trình viên lấy thời gian biên dịch của mã nguồn. Tính năng này hữu ích trong việc ghi lại thông tin về thời gian và giúp theo dõi các phiên bản của chương trình.

## Tài Liệu
Macro `__TIME__` là một hằng số chuỗi được định nghĩa sẵn trong ngôn ngữ C. Nó chứa thời gian biên dịch của chương trình dưới dạng chuỗi với định dạng "HH:MM:SS" (giờ:phút:giây). Thời gian này được cung cấp bởi trình biên dịch và có thể được sử dụng để ghi lại thời gian mà mã nguồn được biên dịch lần cuối.

### Cách Sử Dụng
Macro `__TIME__` có thể được sử dụng trong bất kỳ phần nào của chương trình C. Để truy cập giá trị của nó, bạn chỉ cần sử dụng nó như một chuỗi. Dưới đây là cú pháp cơ bản:

```c
printf("Thời gian biên dịch: %s\n", __TIME__);
```

### Chi Tiết
- **Kiểu Dữ Liệu**: `__TIME__` có kiểu dữ liệu là chuỗi ký tự (string).
- **Giá Trị**: Giá trị của `__TIME__` sẽ thay đổi mỗi khi mã nguồn được biên dịch lại.
- **Tính Khả Dụng**: Tính năng này có sẵn trong hầu hết các trình biên dịch C tiêu chuẩn.

## Ví Dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng `__TIME__` trong một chương trình C:

```c
#include <stdio.h>

int main() {
    printf("Chương trình này được biên dịch vào lúc: %s\n", __TIME__);
    return 0;
}
```

Khi chương trình này được biên dịch và chạy, nó sẽ in ra thời gian biên dịch của mã nguồn.

## Giải Thích
Một số lưu ý quan trọng khi sử dụng `__TIME__`:
- **Thay Đổi Khi Biên Dịch**: Mỗi lần bạn biên dịch lại mã nguồn, giá trị của `__TIME__` sẽ thay đổi. Điều này có thể gây nhầm lẫn nếu bạn không nhận thức được điều này.
- **Không Thay Đổi Tại Thời Gian Chạy**: Giá trị của `__TIME__` không thay đổi trong quá trình thực thi chương trình, mà chỉ giữ nguyên tại thời điểm biên dịch.
- **Không Phải Thời Gian Chạy Thực Tế**: `__TIME__` không phản ánh thời gian thực tế mà chương trình chạy, mà chỉ là thời điểm mà mã nguồn được biên dịch.

## Tóm Tắt Một Dòng
Macro `__TIME__` trong C cung cấp thời gian biên dịch của chương trình dưới dạng chuỗi, hữu ích cho việc ghi lại thông tin phiên bản.