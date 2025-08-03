<!--
Meta Description: # Tìm Hiểu Hàm perror trong Ngôn Ngữ Lập Trình C ## Tóm Tắt Hàm `perror` trong ngôn ngữ lập trình C được sử dụng để in ra thông báo lỗi tương ứng với ...
Meta Keywords: lỗi, perror, thông, báo, trình
-->

# Tìm Hiểu Hàm perror trong Ngôn Ngữ Lập Trình C

## Tóm Tắt
Hàm `perror` trong ngôn ngữ lập trình C được sử dụng để in ra thông báo lỗi tương ứng với mã lỗi toàn cục (global error number) `errno`. Hàm này rất hữu ích trong việc gỡ lỗi và theo dõi các lỗi xảy ra trong quá trình thực thi chương trình.

## Tài Liệu
### Mục Đích
Hàm `perror` cho phép lập trình viên dễ dàng hiển thị thông tin về lỗi mà chương trình gặp phải, giúp nhận diện và khắc phục lỗi nhanh chóng hơn.

### Cú Pháp
```c
#include <stdio.h>
#include <string.h>

void perror(const char *s);
```

### Tham Số
- `s`: Một chuỗi ký tự (string) mô tả ngữ cảnh của lỗi. Nếu `s` là NULL hoặc một chuỗi rỗng, `perror` sẽ chỉ in ra thông báo lỗi.

### Chi Tiết
- Hàm `perror` lấy giá trị của biến toàn cục `errno` để xác định loại lỗi xảy ra và in ra một thông báo lỗi tương ứng.
- Thông báo lỗi được in ra bao gồm chuỗi mô tả từ tham số `s`, theo sau là dấu hai chấm và thông báo lỗi tương ứng với `errno`.
- Để sử dụng hàm `perror`, cần phải bao gồm thư viện `<stdio.h>`.

## Ví Dụ
### Ví dụ Cơ Bản
```c
#include <stdio.h>
#include <errno.h>

int main() {
    FILE *file = fopen("khong_ton_tai.txt", "r");
    if (file == NULL) {
        perror("Lỗi khi mở file");
    }
    return 0;
}
```
**Giải thích**: Nếu file không tồn tại, hàm `perror` sẽ in ra thông báo lỗi như "Lỗi khi mở file: No such file or directory".

### Ví dụ Khác
```c
#include <stdio.h>
#include <string.h>
#include <errno.h>

int main() {
    int result = remove("file_khong_ton_tai.txt");
    if (result != 0) {
        perror("Không thể xóa file");
    }
    return 0;
}
```
**Giải thích**: Nếu không thể xóa file không tồn tại, `perror` sẽ thông báo lỗi tương ứng với mã lỗi.

## Giải Thích
### Những Lưu Ý Chung
- Một số lập trình viên có thể quên thiết lập `errno` trước khi gọi `perror`, dẫn đến thông báo không chính xác.
- `perror` không nên được gọi trong các tình huống mà biến `errno` không được thiết lập, vì nó có thể dẫn đến thông báo lỗi không chính xác hoặc không rõ ràng.
- Thông báo lỗi được in ra trên `stderr`, vì vậy nếu bạn muốn lưu lại thông tin lỗi, hãy chắc chắn rằng bạn xử lý đầu ra này đúng cách.

## Tóm Tắt Một Dòng
Hàm `perror` trong C là công cụ mạnh mẽ để in ra thông báo lỗi chi tiết dựa trên mã lỗi toàn cục `errno`, giúp lập trình viên dễ dàng xác định và khắc phục lỗi trong chương trình.