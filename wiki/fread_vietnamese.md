<!--
Meta Description: # Hàm fread trong C: Đọc Dữ Liệu Từ Tệp ## Tóm Tắt Hàm `fread` trong ngôn ngữ lập trình C được sử dụng để đọc dữ liệu từ một tệp vào bộ nhớ, cho phép ...
Meta Keywords: đọc, tệp, fread, một, liệu
-->

# Hàm fread trong C: Đọc Dữ Liệu Từ Tệp

## Tóm Tắt
Hàm `fread` trong ngôn ngữ lập trình C được sử dụng để đọc dữ liệu từ một tệp vào bộ nhớ, cho phép xử lý các loại dữ liệu nhị phân một cách hiệu quả.

## Tài Liệu
### Mục Đích
Hàm `fread` phục vụ để đọc một số lượng nhất định các phần tử từ một tệp nhị phân vào một vùng nhớ cụ thể.

### Cú Pháp
```c
size_t fread(void *ptr, size_t size, size_t count, FILE *stream);
```

### Tham Số
- `ptr`: Con trỏ đến bộ nhớ nơi dữ liệu sẽ được lưu trữ.
- `size`: Kích thước của mỗi phần tử cần đọc (tính bằng byte).
- `count`: Số lượng phần tử cần đọc.
- `stream`: Con trỏ đến tệp mà bạn muốn đọc từ đó.

### Giá Trị Trả Về
Hàm `fread` trả về số lượng phần tử đã được đọc thành công. Nếu giá trị trả về nhỏ hơn `count`, điều này có thể có nghĩa là đã xảy ra lỗi hoặc đã đạt đến cuối tệp.

## Ví Dụ
### Ví Dụ Cơ Bản
```c
#include <stdio.h>

int main() {
    FILE *file;
    int numbers[10];

    file = fopen("data.bin", "rb");
    if (file == NULL) {
        perror("Không thể mở tệp");
        return 1;
    }

    size_t result = fread(numbers, sizeof(int), 10, file);
    if (result != 10) {
        perror("Lỗi khi đọc tệp");
    }

    fclose(file);
    return 0;
}
```

### Giải Thích Ví Dụ
Trong ví dụ trên, chúng ta mở một tệp nhị phân `data.bin` và đọc 10 số nguyên từ tệp này vào mảng `numbers`. Chúng ta kiểm tra xem số lượng phần tử đã đọc có đúng như mong đợi hay không.

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Kiểm tra lỗi:** Luôn kiểm tra xem con trỏ tệp có phải là `NULL` hay không trước khi sử dụng.
- **Kích thước không hợp lệ:** Đảm bảo rằng kích thước và số lượng phần tử bạn muốn đọc không vượt quá kích thước tệp.
- **Đọc từ tệp không phải nhị phân:** Sử dụng `fread` để đọc tệp văn bản có thể dẫn đến kết quả không chính xác.

### Ghi Chú Thêm
- Để đảm bảo rằng dữ liệu được đọc đúng cách, bạn nên mở tệp với chế độ `rb` (read binary).
- Có thể sử dụng hàm `ferror` để kiểm tra lỗi sau khi gọi `fread`.

## Tóm Tắt Một Dòng
Hàm `fread` trong C cho phép đọc các phần tử dữ liệu nhị phân từ tệp vào bộ nhớ một cách hiệu quả.