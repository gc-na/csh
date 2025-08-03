<!--
Meta Description: # Tìm hiểu về __DATE__ trong ngôn ngữ lập trình C ## Tóm tắt `__DATE__` là một macro được định nghĩa sẵn trong ngôn ngữ C, cho phép lập trình viên lấy...
Meta Keywords: biên, dịch, __date__, được, ngày
-->

# Tìm hiểu về __DATE__ trong ngôn ngữ lập trình C

## Tóm tắt
`__DATE__` là một macro được định nghĩa sẵn trong ngôn ngữ C, cho phép lập trình viên lấy thông tin về ngày biên dịch của mã nguồn. Nó trả về một chuỗi ký tự chứa ngày, tháng và năm mà mã nguồn được biên dịch.

## Tài liệu
Macro `__DATE__` được sử dụng để cung cấp thông tin về ngày biên dịch của một chương trình C. Thông tin này có thể hữu ích cho việc ghi chú phiên bản, thông tin bảo trì, hoặc đơn giản là theo dõi thời gian mà mã nguồn được cập nhật.

### Cách sử dụng
Khi bạn sử dụng `__DATE__` trong mã của mình, nó sẽ được thay thế bằng một chuỗi diễn tả ngày biên dịch theo định dạng "Mmm dd yyyy", trong đó:
- `Mmm` là viết tắt của tháng (ví dụ: Jan, Feb, Mar, ...).
- `dd` là ngày (01 đến 31).
- `yyyy` là năm (ví dụ: 2023).

### Ví dụ
Dưới đây là một ví dụ cơ bản về việc sử dụng `__DATE__` trong chương trình C:

```c
#include <stdio.h>

int main() {
    printf("Mã nguồn được biên dịch vào ngày: %s\n", __DATE__);
    return 0;
}
```

Khi bạn biên dịch và chạy chương trình này, nó sẽ in ra ngày mà chương trình được biên dịch, ví dụ: "Mã nguồn được biên dịch vào ngày: Oct 03 2023".

## Giải thích
Mặc dù `__DATE__` rất hữu ích, có một số điểm cần lưu ý:
- Chuỗi trả về là hằng số và không thể thay đổi.
- `__DATE__` chỉ cung cấp thông tin về ngày biên dịch, không cung cấp thời gian cụ thể.
- Nếu bạn cần thông tin về thời gian, hãy xem xét sử dụng macro `__TIME__`, được định nghĩa tương tự.

Việc sử dụng `__DATE__` không gây ảnh hưởng đến hiệu suất của chương trình, nhưng có thể làm cho mã của bạn trở nên dễ bảo trì hơn bằng cách cung cấp thông tin rõ ràng về thời điểm mà mã đã được biên dịch.

## Tóm tắt một dòng
`__DATE__` là một macro trong C cho phép lấy thông tin về ngày biên dịch của mã nguồn, hữu ích cho việc theo dõi phiên bản và bảo trì.