<!--
Meta Description: # Hàm `memcmp` trong C: So Sánh Các Khối Bộ Nhớ ## Tóm tắt Hàm `memcmp` trong ngôn ngữ lập trình C được sử dụng để so sánh hai khối bộ nhớ. Hàm này là...
Meta Keywords: sánh, hai, khối, nhớ, memcmp
-->

# Hàm `memcmp` trong C: So Sánh Các Khối Bộ Nhớ

## Tóm tắt
Hàm `memcmp` trong ngôn ngữ lập trình C được sử dụng để so sánh hai khối bộ nhớ. Hàm này là một phần của thư viện chuẩn `<string.h>` và rất hữu ích trong việc kiểm tra sự bằng nhau của các mảng hoặc chuỗi.

## Tài liệu
### Mục đích
Hàm `memcmp` so sánh hai khối bộ nhớ byte-by-byte. Nó trả về một giá trị nguyên cho biết kết quả của sự so sánh. Nếu hai khối bộ nhớ giống nhau, hàm trả về 0. Nếu không, nó trả về một giá trị âm hoặc dương tùy thuộc vào việc khối bộ nhớ nào lớn hơn.

### Cú pháp
```c
int memcmp(const void *ptr1, const void *ptr2, size_t num);
```

### Tham số
- `ptr1`: Con trỏ tới khối bộ nhớ đầu tiên.
- `ptr2`: Con trỏ tới khối bộ nhớ thứ hai.
- `num`: Số lượng byte mà bạn muốn so sánh.

### Trả về
- Giá trị < 0: `ptr1` nhỏ hơn `ptr2`.
- Giá trị = 0: `ptr1` bằng `ptr2`.
- Giá trị > 0: `ptr1` lớn hơn `ptr2`.

## Ví dụ
### Ví dụ 1: So sánh hai mảng số nguyên
```c
#include <stdio.h>
#include <string.h>

int main() {
    int arr1[] = {1, 2, 3};
    int arr2[] = {1, 2, 3};
    
    int result = memcmp(arr1, arr2, sizeof(arr1));
    if (result == 0) {
        printf("Hai mảng giống nhau.\n");
    } else {
        printf("Hai mảng khác nhau.\n");
    }
    return 0;
}
```

### Ví dụ 2: So sánh các chuỗi ký tự
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "Hello";
    
    int result = memcmp(str1, str2, sizeof(str1));
    if (result == 0) {
        printf("Hai chuỗi giống nhau.\n");
    } else {
        printf("Hai chuỗi khác nhau.\n");
    }
    return 0;
}
```

## Giải thích
- **Kích thước**: Khi sử dụng `memcmp`, bạn cần đảm bảo kích thước được truyền vào là chính xác. Nếu kích thước lớn hơn kích thước thực tế của một trong hai khối bộ nhớ, hành vi của hàm sẽ không xác định.
- **Kiểu dữ liệu**: `memcmp` so sánh các byte, vì vậy việc so sánh các kiểu dữ liệu khác nhau có thể dẫn đến kết quả không mong muốn. Hãy chắc chắn rằng bạn đang so sánh các khối bộ nhớ có cùng loại dữ liệu.

## Tóm tắt một dòng
Hàm `memcmp` trong C so sánh hai khối bộ nhớ và trả về kết quả dựa trên sự tương đồng của chúng.