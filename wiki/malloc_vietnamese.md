<!--
Meta Description: # malloc trong C: Cách sử dụng và lưu ý quan trọng ## Tóm tắt `malloc` là một hàm trong ngôn ngữ lập trình C dùng để cấp phát bộ nhớ động. Nó cho phép...
Meta Keywords: nhớ, cấp, phát, malloc, int
-->

# malloc trong C: Cách sử dụng và lưu ý quan trọng

## Tóm tắt
`malloc` là một hàm trong ngôn ngữ lập trình C dùng để cấp phát bộ nhớ động. Nó cho phép lập trình viên yêu cầu một khối bộ nhớ nhất định từ heap (bộ nhớ động) và trả về con trỏ đến vị trí bộ nhớ đó.

## Tài liệu

### Mục đích
Hàm `malloc` (memory allocation) được sử dụng để cấp phát bộ nhớ cho các kiểu dữ liệu mà kích thước không xác định tại thời điểm biên dịch. Điều này rất hữu ích cho việc xử lý các cấu trúc dữ liệu như mảng động, danh sách liên kết, và nhiều hơn nữa.

### Cú pháp
```c
void* malloc(size_t size);
```

### Tham số
- `size`: Số byte cần cấp phát. Tham số này phải là một số nguyên dương.

### Trả về
Hàm `malloc` trả về một con trỏ đến vùng bộ nhớ được cấp phát. Nếu không thể cấp phát bộ nhớ, hàm sẽ trả về `NULL`.

### Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng `malloc`.

1. Cấp phát bộ nhớ cho một biến nguyên:
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr;
    ptr = (int*) malloc(sizeof(int));
    if (ptr == NULL) {
        printf("Không thể cấp phát bộ nhớ\n");
        return 1;
    }
    *ptr = 10;
    printf("Giá trị: %d\n", *ptr);
    free(ptr); // Giải phóng bộ nhớ
    return 0;
}
```

2. Cấp phát bộ nhớ cho một mảng:
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    int n = 5;
    arr = (int*) malloc(n * sizeof(int));
    
    if (arr == NULL) {
        printf("Không thể cấp phát bộ nhớ\n");
        return 1;
    }

    for (int i = 0; i < n; i++) {
        arr[i] = i * 2; // Gán giá trị cho mảng
    }

    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    free(arr); // Giải phóng bộ nhớ
    return 0;
}
```

## Giải thích
Khi sử dụng `malloc`, lập trình viên cần lưu ý một số điều sau:

- **Kiểm tra NULL**: Luôn kiểm tra con trỏ trả về từ `malloc` có phải là `NULL` hay không. Nếu `malloc` không thể cấp phát bộ nhớ, nó sẽ trả về `NULL`, và việc truy cập vào con trỏ này sẽ dẫn đến lỗi chạy chương trình (segmentation fault).
  
- **Giải phóng bộ nhớ**: Sau khi sử dụng bộ nhớ được cấp phát, cần sử dụng hàm `free` để giải phóng bộ nhớ, tránh rò rỉ bộ nhớ (memory leak).

- **Kích thước cấp phát**: Khi cấp phát bộ nhớ cho cấu trúc dữ liệu phức tạp, cần đảm bảo rằng kích thước được tính toán chính xác để tránh lỗi tràn bộ nhớ.

## Tóm tắt một dòng
Hàm `malloc` trong C được sử dụng để cấp phát bộ nhớ động, cho phép tạo ra các cấu trúc dữ liệu linh hoạt và hiệu quả.