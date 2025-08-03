<!--
Meta Description: # Từ Khóa "default" Trong Ngôn Ngữ Lập Trình C: Tính Năng Quan Trọng ## Tóm Tắt Từ khóa "default" trong ngôn ngữ lập trình C được sử dụng trong cấu tr...
Meta Keywords: trong, default, không, trường, hợp
-->

# Từ Khóa "default" Trong Ngôn Ngữ Lập Trình C: Tính Năng Quan Trọng

## Tóm Tắt
Từ khóa "default" trong ngôn ngữ lập trình C được sử dụng trong cấu trúc lệnh `switch`, cho phép xác định hành động mặc định khi không có trường hợp nào khớp với giá trị kiểm tra.

## Tài Liệu
### Mục Đích
Từ khóa "default" trong C được sử dụng để chỉ định hành động mà chương trình sẽ thực hiện nếu không có trường hợp nào trong cấu trúc lệnh `switch` khớp với giá trị của biến.

### Cách Sử Dụng
Cú pháp của từ khóa "default" trong cấu trúc `switch` như sau:

```c
switch (biến) {
    case giá_trị_1:
        // Hành động cho giá trị 1
        break;
    case giá_trị_2:
        // Hành động cho giá trị 2
        break;
    default:
        // Hành động mặc định
}
```

Trong đó, `biến` là giá trị được kiểm tra, và các `case` xác định các giá trị cụ thể. Nếu không có `case` nào khớp, chương trình sẽ thực hiện khối lệnh trong phần `default`.

### Chi Tiết
- Từ khóa `default` không phải là bắt buộc. Nếu không có nó, và không có trường hợp nào khớp, chương trình sẽ tiếp tục mà không thực hiện hành động nào.
- Một khối `default` có thể xuất hiện ở bất kỳ vị trí nào trong cấu trúc `switch`, nhưng thường được đặt ở cuối để dễ đọc hơn.
- Việc sử dụng `break` trong các trường hợp và `default` là cần thiết để tránh việc tiếp tục thực hiện các khối lệnh của các trường hợp sau đó.

## Ví Dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng từ khóa `default` trong C:

```c
#include <stdio.h>

int main() {
    int so = 3;

    switch (so) {
        case 1:
            printf("Số là 1\n");
            break;
        case 2:
            printf("Số là 2\n");
            break;
        default:
            printf("Số không phải là 1 hoặc 2\n");
    }

    return 0;
}
```

Khi chạy chương trình này, kết quả sẽ là:
```
Số không phải là 1 hoặc 2
```

## Giải Thích
- **Những cạm bẫy phổ biến**: Một số lập trình viên có thể quên sử dụng `break` trong các trường hợp, dẫn đến việc thực hiện tất cả các khối lệnh sau trường hợp đầu tiên khớp. Điều này có thể gây ra hành vi không mong muốn.
- **Lưu ý**: Từ khóa `default` có thể không cần thiết nếu bạn đã xử lý mọi khả năng có thể xảy ra, nhưng việc thêm nó có thể cung cấp một cách xử lý an toàn cho các trường hợp không lường trước.

## Tóm Tắt Một Dòng
Từ khóa "default" trong C cho phép chỉ định hành động mặc định trong cấu trúc lệnh `switch` khi không có trường hợp nào khớp.