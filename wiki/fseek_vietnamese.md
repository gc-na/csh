<!--
Meta Description: # Hàm fseek trong C: Định vị con trỏ tệp một cách hiệu quả ## Tóm tắt Hàm `fseek` trong C được sử dụng để thay đổi vị trí của con trỏ tệp trong một tệ...
Meta Keywords: tệp, con, trỏ, trí, file
-->

# Hàm fseek trong C: Định vị con trỏ tệp một cách hiệu quả

## Tóm tắt
Hàm `fseek` trong C được sử dụng để thay đổi vị trí của con trỏ tệp trong một tệp đã mở, cho phép bạn truy cập vào các phần khác nhau của tệp một cách linh hoạt.

## Tài liệu
Hàm `fseek` có mục đích chính là thay đổi vị trí của con trỏ tệp trong một tệp. Đây là một phần của thư viện tiêu chuẩn C, nằm trong `<stdio.h>`. Cú pháp cơ bản của hàm là:

```c
int fseek(FILE *stream, long int offset, int whence);
```

### Tham số:
- `stream`: Con trỏ đến tệp mà bạn muốn thay đổi vị trí.
- `offset`: Số byte mà bạn muốn dịch chuyển con trỏ. Có thể là số dương hoặc âm.
- `whence`: Cách thức tham chiếu cho `offset`. Có ba giá trị có thể:
  - `SEEK_SET`: Đặt vị trí con trỏ từ đầu tệp.
  - `SEEK_CUR`: Đặt vị trí con trỏ từ vị trí hiện tại.
  - `SEEK_END`: Đặt vị trí con trỏ từ cuối tệp.

### Giá trị trả về:
Hàm `fseek` trả về 0 nếu thành công và một giá trị khác 0 nếu có lỗi xảy ra.

## Ví dụ
### Ví dụ 1: Di chuyển con trỏ đến vị trí nhất định
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Không thể mở tệp");
        return -1;
    }

    // Di chuyển con trỏ đến byte thứ 10
    fseek(file, 10, SEEK_SET);
    
    // Đọc dữ liệu từ vị trí đã định
    char ch = fgetc(file);
    printf("Ký tự tại vị trí 10: %c\n", ch);

    fclose(file);
    return 0;
}
```

### Ví dụ 2: Di chuyển con trỏ từ vị trí hiện tại
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Không thể mở tệp");
        return -1;
    }

    // Đọc ký tự đầu tiên
    char ch = fgetc(file);
    printf("Ký tự đầu tiên: %c\n", ch);
    
    // Di chuyển con trỏ 5 byte về phía trước
    fseek(file, 5, SEEK_CUR);
    
    // Đọc ký tự tiếp theo
    ch = fgetc(file);
    printf("Ký tự sau khi di chuyển: %c\n", ch);

    fclose(file);
    return 0;
}
```

## Giải thích
Khi sử dụng `fseek`, bạn cần chú ý các điều sau:
- Đảm bảo rằng tệp đã được mở thành công trước khi gọi `fseek`.
- Nếu bạn cố gắng di chuyển con trỏ đến một vị trí ngoài giới hạn của tệp, hàm sẽ trả về lỗi.
- Việc sử dụng `SEEK_CUR` cần được chú ý, vì nếu không cẩn thận, bạn có thể di chuyển ra ngoài giới hạn của tệp.
- Một số hệ điều hành có thể không hỗ trợ việc thay đổi vị trí trong các tệp không tuần tự như socket.

## Tóm tắt một dòng
Hàm `fseek` trong C cho phép thay đổi vị trí con trỏ tệp để truy cập linh hoạt vào các phần khác nhau của tệp.