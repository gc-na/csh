<!--
Meta Description: # Hàm fscanf trong C: Đọc Dữ Liệu Từ Tệp ## Tóm tắt Hàm `fscanf` trong ngôn ngữ lập trình C được sử dụng để đọc dữ liệu từ tệp theo định dạng đã chỉ đ...
Meta Keywords: đọc, tệp, file, liệu, được
-->

# Hàm fscanf trong C: Đọc Dữ Liệu Từ Tệp

## Tóm tắt
Hàm `fscanf` trong ngôn ngữ lập trình C được sử dụng để đọc dữ liệu từ tệp theo định dạng đã chỉ định, cho phép người lập trình thao tác linh hoạt với các tệp văn bản.

## Tài liệu
Hàm `fscanf` được định nghĩa trong thư viện `<stdio.h>`. Mục đích chính của hàm này là đọc dữ liệu từ một tệp đã mở và lưu trữ nó vào các biến tương ứng theo định dạng đã chỉ định.

### Cú pháp
```c
int fscanf(FILE *stream, const char *format, ...);
```

### Tham số
- `stream`: Con trỏ đến tệp mà bạn muốn đọc dữ liệu. Tệp này cần được mở bằng một trong các hàm mở tệp như `fopen`.
- `format`: Chuỗi định dạng mô tả kiểu dữ liệu mà bạn muốn đọc. Nó có thể bao gồm các định dạng như `%d`, `%s`, `%f`, v.v.
- `...`: Danh sách các biến mà giá trị đọc được sẽ được lưu vào.

### Giá trị trả về
Hàm trả về số lượng các đối số thành công được đọc và gán. Nếu có lỗi xảy ra hoặc đến EOF (End of File) trước khi đọc được bất kỳ giá trị nào, hàm sẽ trả về EOF.

## Ví dụ
### Ví dụ 1: Đọc số nguyên từ tệp
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("data.txt", "r");
    int number;

    if (file != NULL) {
        fscanf(file, "%d", &number);
        printf("Số đọc được: %d\n", number);
        fclose(file);
    } else {
        printf("Không thể mở tệp.\n");
    }
    return 0;
}
```

### Ví dụ 2: Đọc chuỗi từ tệp
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("data.txt", "r");
    char str[100];

    if (file != NULL) {
        fscanf(file, "%s", str);
        printf("Chuỗi đọc được: %s\n", str);
        fclose(file);
    } else {
        printf("Không thể mở tệp.\n");
    }
    return 0;
}
```

## Giải thích
Khi sử dụng `fscanf`, người lập trình cần chú ý đến vài vấn đề thường gặp:
- **Sai định dạng**: Nếu định dạng không khớp với dữ liệu trong tệp, `fscanf` sẽ không đọc được dữ liệu và có thể gây ra lỗi.
- **Không đủ bộ nhớ**: Đối với chuỗi, hãy đảm bảo rằng biến lưu trữ có đủ bộ nhớ để chứa dữ liệu.
- **Không kiểm tra giá trị trả về**: Điều quan trọng là kiểm tra giá trị trả về của `fscanf` để đảm bảo rằng dữ liệu đã được đọc thành công.

## Tóm tắt một dòng
Hàm `fscanf` trong C cho phép đọc dữ liệu từ tệp theo định dạng chỉ định và lưu trữ vào các biến tương ứng.