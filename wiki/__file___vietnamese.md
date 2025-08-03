<!--
Meta Description: # Tìm Hiểu về Macro "__FILE__" trong Ngôn Ngữ Lập Trình C ## Tóm tắt Macro `__FILE__` trong ngôn ngữ lập trình C là một hằng số được sử dụng để lấy tê...
Meta Keywords: file, trong, __file__, tên, trình
-->

# Tìm Hiểu về Macro "__FILE__" trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Macro `__FILE__` trong ngôn ngữ lập trình C là một hằng số được sử dụng để lấy tên file nguồn mà đoạn mã đang được biên dịch. Đây là một công cụ hữu ích cho việc gỡ lỗi và quản lý log trong chương trình.

## Tài liệu
### Mục đích
Macro `__FILE__` cung cấp tên của file nguồn hiện tại, cho phép lập trình viên theo dõi và ghi lại thông tin về file mà mã nguồn đang được biên dịch. Điều này đặc biệt hữu ích trong quá trình gỡ lỗi và khi bạn cần thông báo cho người dùng về nguồn gốc của lỗi.

### Cách sử dụng
`__FILE__` có thể được sử dụng trực tiếp trong bất kỳ vị trí nào trong mã nguồn C. Nó thường được kết hợp với các macro khác như `__LINE__` để cung cấp thông tin chi tiết hơn về vị trí của lỗi.

### Chi tiết
- **Kiểu dữ liệu**: `__FILE__` trả về một chuỗi ký tự (string) chứa tên file nguồn.
- **Biên dịch**: Tên file sẽ được xác định tại thời điểm biên dịch, do đó nó không thay đổi trong quá trình thực thi của chương trình.
- **Kết hợp với `__LINE__`**: Bạn có thể sử dụng `__LINE__` cùng với `__FILE__` để báo cáo cả tên file và số dòng, giúp dễ dàng xác định vị trí lỗi trong mã nguồn.

## Ví dụ
```c
#include <stdio.h>

int main() {
    printf("File name: %s\n", __FILE__);
    printf("Line number: %d\n", __LINE__);
    return 0;
}
```
Khi chạy chương trình này, bạn sẽ thấy tên file và số dòng mà lệnh printf được định nghĩa.

## Giải thích
### Những điểm cần lưu ý
- `__FILE__` chỉ cung cấp tên file, không bao gồm đường dẫn đầy đủ. Để có được đường dẫn, bạn cần sử dụng một phương pháp khác.
- Nếu bạn di chuyển đoạn mã sang file khác, tên file in ra sẽ thay đổi tương ứng với file mới.
- Để tránh nhầm lẫn, hãy chắc chắn rằng bạn không sử dụng cùng một tên file cho nhiều file khác nhau trong dự án của bạn.

### Lưu ý thêm
- Việc sử dụng `__FILE__` có thể giúp bạn tạo ra các thông báo log chi tiết, làm cho quá trình gỡ lỗi trở nên dễ dàng hơn.
- Hãy cẩn thận khi sử dụng `__FILE__` trong các macro tùy chỉnh, vì tên file có thể không phản ánh chính xác ngữ cảnh mà macro đó được gọi.

## Tóm tắt một dòng
Macro `__FILE__` trong C cung cấp tên của file nguồn hiện tại, hỗ trợ lập trình viên trong việc gỡ lỗi và theo dõi mã nguồn.