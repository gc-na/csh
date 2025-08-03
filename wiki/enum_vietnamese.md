<!--
Meta Description: # Enum trong C: Định nghĩa, Cách sử dụng và Ví dụ ## Tóm tắt `enum` (liệt kê) trong ngôn ngữ lập trình C là một kiểu dữ liệu cho phép định nghĩa một t...
Meta Keywords: enum, một, các, trong, dụng
-->

# Enum trong C: Định nghĩa, Cách sử dụng và Ví dụ

## Tóm tắt
`enum` (liệt kê) trong ngôn ngữ lập trình C là một kiểu dữ liệu cho phép định nghĩa một tập hợp các hằng số có tên, giúp tăng tính rõ ràng và dễ đọc cho mã nguồn.

## Tài liệu
### Mục đích
Kiểu dữ liệu `enum` được sử dụng để tạo ra các hằng số có tên, cho phép lập trình viên nhóm các giá trị liên quan lại với nhau. Điều này giúp mã nguồn dễ bảo trì và dễ hiểu hơn.

### Cách sử dụng
Để định nghĩa một `enum`, bạn sử dụng cú pháp sau:

```c
enum tên_enum {
    HẰNG_SỐ_1,
    HẰNG_SỐ_2,
    HẰNG_SỐ_3 = giá_trị,
    ...
};
```

- `tên_enum`: Tên của loại enum.
- `HẰNG_SỐ_N`: Tên của các hằng số trong enum, có thể được gán giá trị cụ thể (nếu không, các hằng số sẽ tự động được gán giá trị bắt đầu từ 0).

### Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng `enum` trong C:

```c
#include <stdio.h>

enum DayOfWeek {
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY,
    SUNDAY
};

int main() {
    enum DayOfWeek today;
    today = WEDNESDAY;

    if (today == WEDNESDAY) {
        printf("Hôm nay là thứ Tư.\n");
    }
    return 0;
}
```

### Giải thích
Khi sử dụng `enum`, có một số điểm cần lưu ý:
- Giá trị của các hằng số trong enum bắt đầu từ 0 và tăng dần theo thứ tự, trừ khi bạn chỉ định giá trị cụ thể.
- Enum không tạo ra một kiểu dữ liệu mới mà chỉ là một định danh cho các giá trị hằng số.
- Cần cẩn thận khi sử dụng giá trị của enum, vì nếu không được gán một cách chính xác, có thể dẫn đến lỗi logic trong chương trình.

## Tóm tắt một dòng
`enum` trong C là một kiểu dữ liệu cho phép định nghĩa các hằng số có tên, giúp mã nguồn trở nên rõ ràng và dễ bảo trì.