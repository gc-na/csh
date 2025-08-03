<!--
Meta Description: # Hàm strtok trong C: Tách chuỗi hiệu quả ## Tóm tắt Hàm `strtok` trong C được sử dụng để phân tách một chuỗi thành các token (mảnh) dựa trên các ký t...
Meta Keywords: chuỗi, strtok, một, token, phân
-->

# Hàm strtok trong C: Tách chuỗi hiệu quả

## Tóm tắt
Hàm `strtok` trong C được sử dụng để phân tách một chuỗi thành các token (mảnh) dựa trên các ký tự phân cách được chỉ định. Đây là một công cụ hữu ích cho việc xử lý chuỗi trong lập trình.

## Tài liệu
### Mục đích
Hàm `strtok` được thiết kế để tách một chuỗi thành các phần nhỏ hơn, gọi là token, bằng cách sử dụng một hoặc nhiều ký tự phân cách. Hàm này có thể được sử dụng để phân tích cú pháp chuỗi văn bản, chẳng hạn như tách từ trong một câu hoặc phân tách các giá trị trong một chuỗi CSV.

### Cú pháp
```c
char *strtok(char *str, const char *delim);
```

### Tham số
- `str`: Chuỗi cần tách. Lần gọi đầu tiên của `strtok` nên chứa chuỗi này. Các lần gọi sau nên truyền `NULL` để tiếp tục từ vị trí trước đó.
- `delim`: Chuỗi chứa các ký tự phân cách. Mỗi ký tự trong chuỗi này sẽ được coi là một ký tự phân cách.

### Giá trị trả về
- Trả về một con trỏ đến token tiếp theo. Nếu không còn token nào, hàm sẽ trả về `NULL`.

### Lưu ý
- Hàm `strtok` thay đổi chuỗi gốc bằng cách thay thế các ký tự phân cách bằng ký tự null (`\0`).
- Hàm không an toàn cho đa luồng vì nó sử dụng một biến tĩnh nội bộ để lưu trữ trạng thái giữa các cuộc gọi.

## Ví dụ
### Ví dụ 1: Tách một chuỗi cơ bản
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "C programming is fun";
    char *token = strtok(str, " ");

    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, " ");
    }

    return 0;
}
```
**Kết quả:**
```
C
programming
is
fun
```

### Ví dụ 2: Tách chuỗi với nhiều ký tự phân cách
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "apple,banana;orange|grape";
    char *token = strtok(str, ",;|");

    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, ",;|");
    }

    return 0;
}
```
**Kết quả:**
```
apple
banana
orange
grape
```

## Giải thích
### Những cạm bẫy phổ biến
- **Không sử dụng lại chuỗi gốc**: Vì `strtok` thay đổi chuỗi gốc, nếu cần giữ nguyên chuỗi này, hãy sao chép nó sang một biến khác trước khi gọi hàm.
- **Không an toàn cho đa luồng**: Nếu bạn cần sử dụng `strtok` trong một ứng dụng đa luồng, hãy xem xét sử dụng `strtok_r`, phiên bản an toàn cho đa luồng.
- **Kiểm tra giá trị trả về**: Đảm bảo kiểm tra giá trị trả về từ `strtok` để tránh dereference con trỏ NULL.

## Tóm tắt một câu
Hàm `strtok` trong C là một công cụ mạnh mẽ để tách chuỗi thành các token dựa trên các ký tự phân cách đã chỉ định, nhưng cần cẩn thận với những thay đổi mà nó thực hiện đối với chuỗi gốc.