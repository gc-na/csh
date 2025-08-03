<!--
Meta Description: # Từ Khóa "extern" trong Ngôn Ngữ Lập Trình C ## Tóm tắt Từ khóa `extern` trong ngôn ngữ lập trình C được sử dụng để khai báo một biến hoặc hàm có thể...
Meta Keywords: file, extern, báo, khai, biến
-->

# Từ Khóa "extern" trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Từ khóa `extern` trong ngôn ngữ lập trình C được sử dụng để khai báo một biến hoặc hàm có thể được sử dụng trong các file nguồn khác, giúp chia sẻ và tái sử dụng mã nguồn một cách hiệu quả.

## Tài liệu
### Mục đích
Từ khóa `extern` có mục đích chính là thông báo cho trình biên dịch rằng biến hoặc hàm được khai báo sẽ được định nghĩa ở nơi khác (có thể là trong một file khác hoặc ở một phần khác trong cùng file).

### Cách sử dụng
- **Khai báo biến**: Khi bạn khai báo một biến với từ khóa `extern`, bạn chỉ định rằng biến đó đã được định nghĩa ở đâu đó. Điều này cho phép các file khác trong chương trình có thể truy cập biến đó mà không cần phải định nghĩa lại.
  
  ```c
  extern int count; // Khai báo biến count
  ```

- **Khai báo hàm**: Tương tự, khi khai báo một hàm với từ khóa `extern`, bạn đang cho biết hàm đó được định nghĩa ở một nơi khác, giúp cho việc gọi hàm này từ các file khác.

  ```c
  extern void display(); // Khai báo hàm display
  ```

### Chi tiết
- Biến được khai báo với từ khóa `extern` không chiếm bộ nhớ cho đến khi nó được định nghĩa ở một nơi khác.
- Khi bạn sử dụng `extern`, bạn cần đảm bảo rằng biến hoặc hàm đó thực sự tồn tại trong chương trình, nếu không sẽ dẫn đến lỗi liên kết.
- `extern` có thể được sử dụng trong cả file header và file nguồn.

## Ví dụ
### Ví dụ 1: Khai báo biến
**File 1: file1.c**
```c
#include <stdio.h>

int count = 10; // Định nghĩa biến count

void display() {
    printf("Count is: %d\n", count);
}
```

**File 2: file2.c**
```c
#include <stdio.h>

extern int count; // Khai báo biến count

void displayCount() {
    printf("Count from another file: %d\n", count);
}
```

### Ví dụ 2: Khai báo hàm
**File 1: func.c**
```c
#include <stdio.h>

void greet() {
    printf("Hello, World!\n");
}
```

**File 2: main.c**
```c
#include <stdio.h>

extern void greet(); // Khai báo hàm greet

int main() {
    greet(); // Gọi hàm greet
    return 0;
}
```

## Giải thích
### Những cạm bẫy thường gặp
- **Không định nghĩa**: Nếu bạn khai báo một biến hoặc hàm với từ khóa `extern` nhưng không có định nghĩa tương ứng, bạn sẽ gặp phải lỗi "undefined reference" khi biên dịch.
- **Sử dụng trong file header**: Khi sử dụng `extern` trong file header, hãy chắc chắn rằng file header này được bao gồm chỉ một lần trong mỗi file nguồn để tránh lỗi định nghĩa lặp.

### Ghi chú bổ sung
- Từ khóa `extern` là rất hữu ích trong lập trình lớn, nơi mà mã nguồn được chia thành nhiều file khác nhau. Nó giúp duy trì tính tổ chức và dễ bảo trì cho chương trình.

## Tóm tắt một dòng
Từ khóa `extern` trong C cho phép khai báo biến và hàm có thể được sử dụng từ các file nguồn khác, hỗ trợ việc chia sẻ mã nguồn hiệu quả.