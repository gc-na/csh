<!--
Meta Description: # Hàm fwrite trong lập trình C: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Hàm `fwrite` trong ngôn ngữ lập trình C được sử dụng để ghi dữ liệu từ bộ nhớ v...
Meta Keywords: ghi, file, liệu, tệp, fwrite
-->

# Hàm fwrite trong lập trình C: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Hàm `fwrite` trong ngôn ngữ lập trình C được sử dụng để ghi dữ liệu từ bộ nhớ vào tệp. Nó là một phần quan trọng trong việc xử lý tệp nhị phân, cho phép lập trình viên dễ dàng lưu trữ cấu trúc dữ liệu phức tạp.

## Tài liệu
### Mục đích
Hàm `fwrite` cho phép ghi một khối dữ liệu từ bộ nhớ vào một tệp đã mở. Hàm này thường được sử dụng khi bạn cần ghi các loại dữ liệu không phải ký tự, chẳng hạn như mảng hoặc cấu trúc.

### Cú pháp
```c
size_t fwrite(const void *ptr, size_t size, size_t count, FILE *stream);
```

### Tham số
- `ptr`: Con trỏ đến vùng nhớ chứa dữ liệu cần ghi.
- `size`: Kích thước của một phần tử.
- `count`: Số lượng phần tử cần ghi.
- `stream`: Con trỏ đến tệp (FILE*) mà bạn muốn ghi dữ liệu vào.

### Giá trị trả về
Hàm `fwrite` trả về số lượng phần tử đã được ghi thành công. Nếu giá trị này nhỏ hơn `count`, điều đó có thể cho thấy có lỗi xảy ra trong quá trình ghi.

## Ví dụ
### Ví dụ 1: Ghi một mảng số nguyên vào tệp
```c
#include <stdio.h>

int main() {
    FILE *file;
    int numbers[] = {1, 2, 3, 4, 5};
    size_t count;

    file = fopen("numbers.dat", "wb");
    if (file == NULL) {
        perror("Không thể mở tệp");
        return 1;
    }

    count = fwrite(numbers, sizeof(int), 5, file);
    printf("Đã ghi %zu phần tử vào tệp.\n", count);

    fclose(file);
    return 0;
}
```

### Ví dụ 2: Ghi một cấu trúc vào tệp
```c
#include <stdio.h>
#include <string.h>

struct Student {
    char name[50];
    int age;
};

int main() {
    FILE *file;
    struct Student student = {"Nguyễn Văn A", 20};

    file = fopen("student.dat", "wb");
    if (file == NULL) {
        perror("Không thể mở tệp");
        return 1;
    }

    fwrite(&student, sizeof(struct Student), 1, file);
    fclose(file);
    return 0;
}
```

## Giải thích
### Những cạm bẫy phổ biến
- **Lỗi mở tệp**: Luôn kiểm tra xem tệp có được mở thành công trước khi ghi dữ liệu. Nếu không mở được, hàm `fwrite` sẽ không thể ghi dữ liệu.
- **Kích thước không chính xác**: Đảm bảo rằng kích thước của mỗi phần tử (`size`) và số lượng phần tử (`count`) được thiết lập đúng để tránh ghi sai dữ liệu.
- **Kiểm tra giá trị trả về**: Luôn kiểm tra giá trị trả về của `fwrite` để phát hiện lỗi trong quá trình ghi dữ liệu.

## Tóm tắt một dòng
Hàm `fwrite` trong C cho phép ghi dữ liệu từ bộ nhớ vào tệp nhị phân một cách hiệu quả.