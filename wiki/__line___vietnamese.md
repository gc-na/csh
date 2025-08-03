<!--
Meta Description: # Tìm Hiểu Về Macro `__LINE__` Trong Ngôn Ngữ Lập Trình C ## Tóm Tắt Macro `__LINE__` trong C là một tính năng hữu ích cho phép lập trình viên lấy số ...
Meta Keywords: trong, __line__, dòng, lỗi, macro
-->

# Tìm Hiểu Về Macro `__LINE__` Trong Ngôn Ngữ Lập Trình C

## Tóm Tắt
Macro `__LINE__` trong C là một tính năng hữu ích cho phép lập trình viên lấy số dòng hiện tại trong mã nguồn đang được biên dịch. Tính năng này thường được sử dụng trong các thông báo gỡ lỗi và theo dõi lỗi.

## Tài Liệu
### Mục Đích
Macro `__LINE__` cung cấp một cách đơn giản để xác định vị trí dòng trong tệp mã nguồn của bạn. Khi được sử dụng, nó sẽ trả về số dòng mà nó xuất hiện trong mã nguồn. Điều này rất hữu ích trong việc gỡ lỗi và ghi lại thông tin chi tiết về lỗi.

### Cách Sử Dụng
Macro `__LINE__` không cần bất kỳ tham số nào và có thể được sử dụng trực tiếp trong mã nguồn. Bạn chỉ cần viết `__LINE__` ở bất kỳ vị trí nào trong mã và nó sẽ trả về số dòng tương ứng.

### Chi Tiết
- `__LINE__` là một macro được định nghĩa sẵn trong ngôn ngữ C.
- Giá trị của `__LINE__` là số nguyên, và nó sẽ thay đổi tùy theo vị trí của nó trong mã nguồn.
- Tính năng này rất hữu ích cho việc ghi chú và thông báo lỗi, giúp lập trình viên nhanh chóng xác định được vị trí của vấn đề.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng `__LINE__`:

```c
#include <stdio.h>

int main() {
    printf("Dòng hiện tại là: %d\n", __LINE__); // In ra số dòng hiện tại
    printf("Dòng tiếp theo là: %d\n", __LINE__); // In ra số dòng tiếp theo
    return 0;
}
```
**Kết quả:**
```
Dòng hiện tại là: 5
Dòng tiếp theo là: 6
```

## Giải Thích
### Những Lưu Ý Thường Gặp
- **Không Thay Đổi Giá Trị:** Giá trị của `__LINE__` không thay đổi khi bạn di chuyển mã nguồn. Nó luôn phản ánh số dòng thực tế trong tệp mã nguồn.
- **Dùng Trong Macro Khác:** Khi sử dụng `__LINE__` trong một macro khác, hãy nhớ rằng giá trị trả về có thể không giống như bạn mong đợi nếu macro đó được gọi từ nhiều vị trí khác nhau.
- **Gỡ Lỗi:** `__LINE__` thường được kết hợp với `__FILE__` để cung cấp thông tin đầy đủ hơn về vị trí lỗi trong mã, ví dụ: `printf("Lỗi ở %s, dòng %d\n", __FILE__, __LINE__);`.

## Tóm Tắt Một Dòng
Macro `__LINE__` trong C cung cấp số dòng hiện tại của mã nguồn, rất hữu ích cho việc gỡ lỗi và theo dõi lỗi.