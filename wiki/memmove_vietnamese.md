<!--
Meta Description: # Hàm `memmove` trong C: Sao chép bộ nhớ an toàn ## Tóm tắt Hàm `memmove` trong ngôn ngữ lập trình C được sử dụng để sao chép một vùng nhớ từ vị trí n...
Meta Keywords: vùng, nhớ, memmove, một, sao
-->

# Hàm `memmove` trong C: Sao chép bộ nhớ an toàn

## Tóm tắt
Hàm `memmove` trong ngôn ngữ lập trình C được sử dụng để sao chép một vùng nhớ từ vị trí này sang vị trí khác, với khả năng xử lý trường hợp vùng nhớ chồng lên nhau một cách an toàn.

## Tài liệu

### Mục đích
Hàm `memmove` có tác dụng sao chép một số byte từ một vùng nhớ nguồn đến một vùng nhớ đích. Điều đặc biệt của hàm này là nó cho phép sao chép trong trường hợp vùng nguồn và vùng đích có thể chồng lấp lên nhau, điều mà hàm `memcpy` không thể làm một cách an toàn.

### Cú pháp
```c
void *memmove(void *dest, const void *src, size_t n);
```

### Tham số
- `dest`: Vùng nhớ đích nơi dữ liệu sẽ được sao chép đến.
- `src`: Vùng nhớ nguồn từ đó dữ liệu sẽ được sao chép.
- `n`: Số byte sẽ được sao chép.

### Giá trị trả về
Hàm `memmove` trả về con trỏ đến vùng nhớ đích (`dest`).

## Ví dụ

### Ví dụ cơ bản
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello, World!";
    
    // Sao chép từ vị trí 7 đến vị trí 0
    memmove(str, str + 7, 6);
    str[6] = '\0'; // Thêm ký tự kết thúc chuỗi

    printf("%s\n", str); // Kết quả: World!
    return 0;
}
```

### Ví dụ với vùng chồng lấp
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "abcdef";
    
    // Di chuyển một phần của chuỗi trong chính nó
    memmove(str + 2, str, 4);
    printf("%s\n", str); // Kết quả: ababcd
    return 0;
}
```

## Giải thích
- **Nguyên lý hoạt động**: Khi vùng nguồn và vùng đích chồng lên nhau, `memmove` sử dụng một bộ nhớ tạm thời để đảm bảo dữ liệu không bị ghi đè.
- **Nguy cơ phổ biến**: Sử dụng `memcpy` thay cho `memmove` khi có chồng lấp có thể dẫn đến kết quả không mong muốn hoặc lỗi.
- **Kích thước**: Đảm bảo rằng kích thước `n` không vượt quá kích thước của vùng nhớ đích hoặc nguồn để tránh các vấn đề liên quan đến truy cập bộ nhớ ngoài giới hạn.

## Tóm tắt một câu
Hàm `memmove` là một công cụ mạnh mẽ trong C để sao chép dữ liệu giữa các vùng nhớ, xử lý an toàn các tình huống có vùng chồng lấp.