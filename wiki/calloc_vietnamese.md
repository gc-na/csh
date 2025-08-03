<!--
Meta Description: # Hàm calloc trong C: Cấp phát bộ nhớ động hiệu quả ## Tóm tắt Hàm `calloc` trong ngôn ngữ lập trình C được sử dụng để cấp phát bộ nhớ động cho một mả...
Meta Keywords: nhớ, cấp, phát, calloc, dụng
-->

# Hàm calloc trong C: Cấp phát bộ nhớ động hiệu quả

## Tóm tắt
Hàm `calloc` trong ngôn ngữ lập trình C được sử dụng để cấp phát bộ nhớ động cho một mảng các đối tượng và khởi tạo tất cả các byte của bộ nhớ được cấp phát thành 0.

## Tài liệu
Hàm `calloc` có cú pháp như sau:

```c
void* calloc(size_t num, size_t size);
```

### Mục đích
Hàm `calloc` được sử dụng để cấp phát bộ nhớ cho `num` đối tượng, mỗi đối tượng có kích thước `size` byte. Bộ nhớ được cấp phát sẽ được khởi tạo với giá trị 0, giúp tránh tình trạng sử dụng dữ liệu không xác định.

### Tham số
- `num`: Số lượng đối tượng cần cấp phát.
- `size`: Kích thước của mỗi đối tượng (tính bằng byte).

### Trả về
Hàm `calloc` trả về một con trỏ đến vùng bộ nhớ đã cấp phát. Nếu việc cấp phát thất bại, nó sẽ trả về `NULL`.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng hàm `calloc`:

### Ví dụ 1: Cấp phát bộ nhớ cho một mảng số nguyên
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    size_t n = 5;

    arr = (int*)calloc(n, sizeof(int));
    if (arr == NULL) {
        printf("Cấp phát bộ nhớ không thành công!\n");
        return 1;
    }

    for (size_t i = 0; i < n; i++) {
        printf("arr[%zu] = %d\n", i, arr[i]); // Tất cả đều là 0
    }

    free(arr); // Giải phóng vùng nhớ
    return 0;
}
```

### Ví dụ 2: Cấp phát bộ nhớ cho một mảng cấu trúc
```c
#include <stdio.h>
#include <stdlib.h>

typedef struct {
    int id;
    char name[20];
} Student;

int main() {
    Student *students;
    size_t n = 3;

    students = (Student*)calloc(n, sizeof(Student));
    if (students == NULL) {
        printf("Cấp phát bộ nhớ không thành công!\n");
        return 1;
    }

    for (size_t i = 0; i < n; i++) {
        printf("Student %zu: id = %d, name = %s\n", i, students[i].id, students[i].name); // id = 0, name = ""
    }

    free(students); // Giải phóng vùng nhớ
    return 0;
}
```

## Giải thích
- **Cấp phát thất bại**: Nếu `calloc` không thể cấp phát bộ nhớ (do thiếu bộ nhớ), nó sẽ trả về `NULL`. Do đó, luôn cần kiểm tra xem con trỏ trả về có phải là `NULL` hay không trước khi sử dụng.
- **Giá trị khởi tạo**: Một điểm khác biệt quan trọng giữa `calloc` và `malloc` là `calloc` khởi tạo tất cả các byte trong vùng bộ nhớ được cấp phát thành 0, trong khi `malloc` không có hành vi này.
- **Giải phóng bộ nhớ**: Sau khi hoàn tất sử dụng bộ nhớ đã cấp phát, hãy luôn sử dụng `free` để giải phóng, tránh rò rỉ bộ nhớ.

## Tóm tắt một dòng
Hàm `calloc` trong C cấp phát bộ nhớ cho mảng đối tượng và khởi tạo tất cả các byte thành 0, giúp tối ưu hóa việc sử dụng bộ nhớ.