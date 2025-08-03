<!--
Meta Description: # Hàm "free" trong C: Giải phóng Bộ Nhớ Động ## Tóm tắt Hàm `free` trong ngôn ngữ lập trình C được sử dụng để giải phóng bộ nhớ mà đã được cấp phát độ...
Meta Keywords: nhớ, giải, phóng, không, free
-->

# Hàm "free" trong C: Giải phóng Bộ Nhớ Động

## Tóm tắt
Hàm `free` trong ngôn ngữ lập trình C được sử dụng để giải phóng bộ nhớ mà đã được cấp phát động bằng cách sử dụng các hàm như `malloc`, `calloc`, hoặc `realloc`. Việc giải phóng bộ nhớ không còn cần thiết giúp ngăn ngừa rò rỉ bộ nhớ và tối ưu hóa hiệu suất của chương trình.

## Tài liệu

### Mục đích
Hàm `free` là một phần của thư viện chuẩn C (stdlib.h) và có vai trò quan trọng trong việc quản lý bộ nhớ. Khi bạn sử dụng các hàm cấp phát bộ nhớ động, bạn cần phải giải phóng bộ nhớ đó khi không còn cần thiết để tránh tình trạng rò rỉ bộ nhớ.

### Cú pháp
```c
void free(void *ptr);
```

- **ptr**: Con trỏ đến vùng nhớ mà bạn muốn giải phóng. Nếu con trỏ này là `NULL`, hàm `free` sẽ không thực hiện hành động gì.

### Chi tiết
- Trước khi gọi hàm `free`, bạn phải đảm bảo rằng con trỏ không trỏ đến vùng bộ nhớ đã được giải phóng trước đó, vì việc này có thể dẫn đến hành vi không xác định.
- Sau khi gọi hàm `free`, con trỏ không được tự động đặt thành `NULL`, vì vậy bạn nên đặt lại con trỏ về `NULL` sau khi giải phóng để tránh tình huống truy cập bộ nhớ không hợp lệ.

## Ví dụ

### Ví dụ 1: Giải phóng bộ nhớ đơn giản
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr = (int*)malloc(5 * sizeof(int)); // Cấp phát bộ nhớ cho mảng 5 số nguyên
    if (arr == NULL) {
        printf("Cấp phát bộ nhớ thất bại!\n");
        return 1;
    }

    // Sử dụng mảng arr...

    free(arr); // Giải phóng bộ nhớ
    arr = NULL; // Đặt lại con trỏ
    return 0;
}
```

### Ví dụ 2: Giải phóng bộ nhớ với con trỏ NULL
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr = NULL;

    free(ptr); // Không có hành động nào xảy ra vì ptr là NULL

    return 0;
}
```

## Giải thích
- **Rò rỉ bộ nhớ**: Nếu bạn không giải phóng bộ nhớ sau khi sử dụng, chương trình của bạn có thể gây ra rò rỉ bộ nhớ, dẫn đến việc tiêu tốn không gian bộ nhớ không cần thiết.
- **Truy cập bộ nhớ không hợp lệ**: Nếu bạn cố gắng truy cập bộ nhớ đã được giải phóng, điều này có thể dẫn đến các lỗi khó chẩn đoán. Để tránh điều này, hãy luôn đặt con trỏ về `NULL` sau khi giải phóng.
- **Nhiều lần giải phóng**: Gọi hàm `free` nhiều lần cho cùng một con trỏ có thể dẫn đến lỗi và hành vi không xác định.

## Tóm tắt một dòng
Hàm `free` trong C được sử dụng để giải phóng bộ nhớ đã cấp phát động, giúp ngăn ngừa rò rỉ bộ nhớ và tối ưu hóa hiệu suất chương trình.