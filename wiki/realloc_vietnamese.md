<!--
Meta Description: # Hàm realloc trong ngôn ngữ lập trình C: Cách sử dụng và lưu ý ## Tóm tắt Hàm `realloc` trong ngôn ngữ lập trình C được sử dụng để thay đổi kích thướ...
Meta Keywords: nhớ, vùng, realloc, arr, int
-->

# Hàm realloc trong ngôn ngữ lập trình C: Cách sử dụng và lưu ý

## Tóm tắt
Hàm `realloc` trong ngôn ngữ lập trình C được sử dụng để thay đổi kích thước vùng nhớ đã cấp phát trước đó, cho phép mở rộng hoặc thu hẹp vùng nhớ một cách linh hoạt.

## Tài liệu
### Mục đích
Hàm `realloc` cho phép lập trình viên thay đổi kích thước một vùng nhớ đã được cấp phát bởi hàm `malloc` hoặc `calloc`. Điều này rất hữu ích khi bạn cần điều chỉnh kích thước của vùng nhớ mà không cần phải sao chép dữ liệu thủ công ra một vùng nhớ mới.

### Cú pháp
```c
void* realloc(void* ptr, size_t new_size);
```

### Tham số
- `ptr`: Con trỏ tới vùng nhớ đã được cấp phát trước đó. Nếu `ptr` là NULL, `realloc` hoạt động giống như `malloc`.
- `new_size`: Kích thước mới của vùng nhớ mà bạn muốn cấp phát (tính bằng byte).

### Trả về
- Trả về con trỏ tới vùng nhớ đã được điều chỉnh kích thước. Nếu việc cấp phát không thành công, nó sẽ trả về NULL, và vùng nhớ gốc vẫn được giữ nguyên.

### Lưu ý
- Nếu `new_size` bằng 0, `realloc` sẽ giải phóng vùng nhớ và trả về NULL.
- Khi `realloc` thành công, vùng nhớ cũ sẽ bị giải phóng tự động.

## Ví dụ
### Ví dụ 1: Mở rộng vùng nhớ
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int* arr = malloc(5 * sizeof(int));
    if (arr == NULL) {
        return 1; // Kiểm tra lỗi
    }

    // Gán giá trị cho mảng
    for (int i = 0; i < 5; i++) {
        arr[i] = i + 1;
    }

    // Thay đổi kích thước mảng
    arr = realloc(arr, 10 * sizeof(int));
    if (arr == NULL) {
        return 1; // Kiểm tra lỗi
    }

    // Gán giá trị cho phần mở rộng
    for (int i = 5; i < 10; i++) {
        arr[i] = i + 1;
    }

    // In ra các giá trị
    for (int i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }

    free(arr);
    return 0;
}
```

### Ví dụ 2: Giải phóng vùng nhớ
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int* arr = malloc(5 * sizeof(int));

    // Giải phóng vùng nhớ bằng realloc
    arr = realloc(arr, 0);
    if (arr == NULL) {
        printf("Vùng nhớ đã được giải phóng.\n");
    }

    return 0;
}
```

## Giải thích
- **Lỗi phổ biến**: Một lỗi thường gặp là không kiểm tra giá trị trả về của `realloc`. Nếu không kiểm tra, bạn có thể vô tình làm mất đi con trỏ tới vùng nhớ cũ, dẫn đến rò rỉ bộ nhớ.
- **Kích thước không hợp lệ**: Khi `new_size` là 0, vùng nhớ sẽ bị giải phóng nhưng không có thông báo nào, điều này có thể gây khó khăn trong việc theo dõi bộ nhớ.
- **Tránh rò rỉ bộ nhớ**: Nếu `realloc` không thành công, con trỏ cũ vẫn giữ nguyên và bạn nên xử lý tình huống này để tránh rò rỉ bộ nhớ.

## Tóm tắt một dòng
Hàm `realloc` trong C cho phép thay đổi kích thước vùng nhớ đã cấp phát, giúp quản lý bộ nhớ hiệu quả hơn.