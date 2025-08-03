<!--
Meta Description: # Từ Khóa "static" trong Ngôn Ngữ Lập Trình C: Hiểu và Sử Dụng ## Tóm Tắt Từ khóa `static` trong ngôn ngữ lập trình C được sử dụng để xác định thời gi...
Meta Keywords: hàm, tĩnh, được, gọi, static
-->

# Từ Khóa "static" trong Ngôn Ngữ Lập Trình C: Hiểu và Sử Dụng

## Tóm Tắt
Từ khóa `static` trong ngôn ngữ lập trình C được sử dụng để xác định thời gian sống và phạm vi của biến và hàm. Nó cho phép biến giữ giá trị của nó giữa các lần gọi hàm và giới hạn khả năng truy cập của hàm trong một tệp nguồn.

## Tài Liệu
Từ khóa `static` có hai ứng dụng chính trong ngôn ngữ C:

1. **Biến tĩnh (Static Variables)**: Khi được khai báo bên trong một hàm, biến tĩnh sẽ giữ giá trị của nó giữa các lần gọi hàm. Điều này có nghĩa là biến sẽ không bị khởi tạo lại mỗi khi hàm được gọi, mà sẽ giữ giá trị từ lần gọi trước đó.

   ```c
   void function() {
       static int count = 0; // Biến tĩnh
       count++;
       printf("%d\n", count);
   }
   ```

2. **Hàm tĩnh (Static Functions)**: Khi một hàm được khai báo là tĩnh, nó chỉ có thể được gọi từ trong tệp nguồn mà nó được định nghĩa. Điều này giúp ngăn ngừa xung đột tên hàm giữa các tệp khác nhau trong cùng một dự án.

   ```c
   static void helperFunction() {
       // Hàm chỉ có thể được gọi từ tệp này
   }
   ```

### Mục Đích và Sử Dụng
- **Giữ lại giá trị**: Biến tĩnh giúp giữ lại giá trị qua nhiều lần gọi hàm.
- **Giới hạn phạm vi**: Hàm tĩnh ngăn chặn việc sử dụng hàm từ bên ngoài tệp, đảm bảo tính đóng gói và giảm xung đột tên.

## Ví Dụ
Dưới đây là một vài ví dụ minh họa về cách sử dụng từ khóa `static` trong ngôn ngữ C:

### Ví dụ 1: Biến Tĩnh
```c
#include <stdio.h>

void countCalls() {
    static int callCount = 0; // Biến tĩnh
    callCount++;
    printf("Hàm đã được gọi %d lần\n", callCount);
}

int main() {
    countCalls();
    countCalls();
    countCalls();
    return 0;
}
```
**Kết quả**:
```
Hàm đã được gọi 1 lần
Hàm đã được gọi 2 lần
Hàm đã được gọi 3 lần
```

### Ví dụ 2: Hàm Tĩnh
```c
#include <stdio.h>

static void displayMessage() {
    printf("Đây là một thông điệp từ hàm tĩnh.\n");
}

int main() {
    displayMessage();
    return 0;
}
```

## Giải Thích
Một số lưu ý quan trọng khi sử dụng từ khóa `static`:

- **Thời gian sống**: Biến tĩnh có thời gian sống tồn tại trong suốt thời gian thực thi của chương trình, không phải chỉ trong phạm vi khối lệnh.
- **Không khởi tạo lại**: Biến tĩnh chỉ được khởi tạo một lần duy nhất, tại thời điểm đầu tiên nó được sử dụng.
- **Giới hạn truy cập**: Hàm tĩnh giúp bảo vệ mã nguồn khỏi việc bị gọi từ nơi khác, giúp duy trì tính toàn vẹn và bảo mật của mã.

## Tóm Tắt Một Dòng
Từ khóa `static` trong C giúp duy trì giá trị của biến qua nhiều lần gọi hàm và giới hạn phạm vi của hàm trong tệp nguồn, nâng cao tính bảo mật và quản lý bộ nhớ.