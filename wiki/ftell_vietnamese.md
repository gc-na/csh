<!--
Meta Description: # Hàm ftell trong ngôn ngữ lập trình C: Tìm vị trí con trỏ trong tệp ## Tóm tắt Hàm `ftell` trong ngôn ngữ C được sử dụng để xác định vị trí hiện tại ...
Meta Keywords: tệp, trí, ftell, hàm, trong
-->

# Hàm ftell trong ngôn ngữ lập trình C: Tìm vị trí con trỏ trong tệp

## Tóm tắt
Hàm `ftell` trong ngôn ngữ C được sử dụng để xác định vị trí hiện tại của con trỏ tệp trong một tệp đã mở, trả về vị trí đó tính bằng byte từ đầu tệp.

## Tài liệu
Hàm `ftell` có mục đích chính là cho phép lập trình viên biết được vị trí hiện tại của con trỏ tệp trong một tệp. Điều này rất hữu ích khi bạn cần quản lý vị trí đọc/ghi trong tệp, chẳng hạn như khi xử lý tệp nhị phân hoặc văn bản.

### Cú pháp
```c
long ftell(FILE *stream);
```

### Tham số
- `stream`: con trỏ tới tệp mà bạn muốn kiểm tra vị trí.

### Giá trị trả về
- Hàm trả về vị trí hiện tại của con trỏ tệp tính bằng byte từ đầu tệp nếu thành công.
- Nếu có lỗi xảy ra, hàm trả về `-1L` và thiết lập biến `errno` để phản ánh lỗi.

### Lưu ý
Trước khi gọi `ftell`, tệp cần phải được mở bằng các hàm như `fopen`. Nếu tệp không mở hoặc đã đóng, hàm sẽ không hoạt động chính xác.

## Ví dụ
### Ví dụ cơ bản
Dưới đây là một ví dụ đơn giản sử dụng `ftell` để kiểm tra vị trí con trỏ trong tệp.

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    if (file == NULL) {
        perror("Không thể mở tệp");
        return 1;
    }

    // Đọc 10 ký tự từ tệp
    char buffer[11];
    fread(buffer, sizeof(char), 10, file);
    buffer[10] = '\0'; // Đảm bảo chuỗi kết thúc đúng

    // Kiểm tra vị trí hiện tại
    long position = ftell(file);
    if (position != -1) {
        printf("Vị trí hiện tại của con trỏ tệp là: %ld\n", position);
    } else {
        perror("Lỗi khi lấy vị trí");
    }

    fclose(file);
    return 0;
}
```

## Giải thích
Khi sử dụng hàm `ftell`, có một số điều cần lưu ý:
- Không nên gọi `ftell` trên một tệp đã bị đóng, vì điều này có thể dẫn đến hành vi không xác định.
- Đối với các tệp nhị phân, vị trí trả về có thể không giống với các tệp văn bản do cách xử lý byte.
- Luôn kiểm tra giá trị trả về của `ftell` để đảm bảo rằng không có lỗi đã xảy ra trong quá trình thực hiện.

## Tóm tắt một dòng
Hàm `ftell` cho phép xác định vị trí hiện tại của con trỏ tệp trong ngôn ngữ lập trình C, hỗ trợ quản lý đọc/ghi tệp hiệu quả.