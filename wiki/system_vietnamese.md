<!--
Meta Description: # Hệ thống (system) trong Ngôn ngữ Lập trình C ## Tóm tắt Hàm `system` trong C được sử dụng để thực thi lệnh hệ thống từ chương trình C, cho phép ngườ...
Meta Keywords: lệnh, thực, thi, system, các
-->

# Hệ thống (system) trong Ngôn ngữ Lập trình C

## Tóm tắt
Hàm `system` trong C được sử dụng để thực thi lệnh hệ thống từ chương trình C, cho phép người lập trình gọi các lệnh shell và nhận kết quả trả về.

## Tài liệu

### Mục đích
Hàm `system` là một phần của thư viện tiêu chuẩn C, được định nghĩa trong `<stdlib.h>`. Nó cho phép lập trình viên thực thi các lệnh shell như trên dòng lệnh của hệ điều hành.

### Cú pháp
```c
int system(const char *command);
```

### Tham số
- `command`: Một chuỗi ký tự (string) chứa lệnh shell mà bạn muốn thực thi.

### Giá trị trả về
- Nếu lệnh thực thi thành công, hàm trả về giá trị khác 0, thường là mã thoát của lệnh đó.
- Nếu có lỗi xảy ra hoặc hàm không thực thi được, hàm trả về -1.

### Lưu ý
Hàm `system` có thể không an toàn khi nhận đầu vào từ người dùng do khả năng bị tấn công qua lệnh shell. Ngoài ra, việc thực thi các lệnh không an toàn có thể dẫn đến rủi ro bảo mật.

## Ví dụ

### Ví dụ 1: Thực thi lệnh đơn giản
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int result = system("ls -l");
    return result;
}
```
Trong ví dụ này, chương trình thực thi lệnh `ls -l` để liệt kê các tệp trong thư mục hiện tại.

### Ví dụ 2: Thực thi lệnh với biến môi trường
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int result = system("echo $HOME");
    return result;
}
```
Ví dụ này sử dụng lệnh `echo` để hiển thị biến môi trường `$HOME`, cho biết thư mục chính của người dùng.

## Giải thích

### Các vấn đề thường gặp
- **Bảo mật**: Tránh sử dụng `system` với đầu vào không được kiểm soát, vì điều này có thể dẫn đến các lỗ hổng bảo mật.
- **Tương thích hệ điều hành**: Lệnh được thực thi qua `system` phụ thuộc vào hệ điều hành, vì vậy cần đảm bảo lệnh đó tồn tại trên hệ thống đang chạy.
- **Chờ đợi lệnh hoàn thành**: Hàm `system` sẽ đợi cho lệnh được thực thi xong trước khi tiếp tục thực hiện các phần khác của chương trình.

### Ghi chú thêm
Việc sử dụng `system` có thể ảnh hưởng đến hiệu suất của chương trình, vì nó tạo ra một shell mới để thực thi lệnh. Trong các ứng dụng cần hiệu suất cao, nên xem xét các phương pháp khác như sử dụng `fork` và `exec`.

## Tóm tắt một dòng
Hàm `system` trong C cho phép thực thi lệnh shell từ chương trình, nhưng cần lưu ý về vấn đề bảo mật và hiệu suất.