<!--
Meta Description: # Hàm toupper trong C: Chuyển đổi ký tự thành chữ hoa ## Tóm tắt Hàm `toupper` trong ngôn ngữ lập trình C được sử dụng để chuyển đổi ký tự từ chữ thườ...
Meta Keywords: chữ, hàm, toupper, hoa, đổi
-->

# Hàm toupper trong C: Chuyển đổi ký tự thành chữ hoa

## Tóm tắt
Hàm `toupper` trong ngôn ngữ lập trình C được sử dụng để chuyển đổi ký tự từ chữ thường (lowercase) thành chữ hoa (uppercase). Hàm này là một phần của thư viện tiêu chuẩn `<ctype.h>` và rất hữu ích trong việc xử lý văn bản.

## Tài liệu
### Mục đích
Hàm `toupper` được thiết kế để kiểm tra và chuyển đổi một ký tự nhất định thành ký tự chữ hoa tương ứng. Nếu ký tự đã là chữ hoa hoặc không phải là ký tự chữ cái, hàm sẽ trả về ký tự gốc.

### Cú pháp
```c
#include <ctype.h>

int toupper(int c);
```

### Tham số
- `c`: Là ký tự (hoặc giá trị nguyên) mà bạn muốn chuyển đổi. Tham số này thường là kiểu `int`, nhưng thường được truyền vào là một ký tự.

### Trả về
- Hàm `toupper` trả về ký tự chữ hoa tương ứng nếu ký tự đầu vào là chữ thường. Nếu ký tự đã là chữ hoa hoặc không phải là chữ cái, hàm sẽ trả về ký tự gốc.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng hàm `toupper`:

### Ví dụ 1: Chuyển đổi một ký tự
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'b';
    char upperCh = toupper(ch);
    printf("Ký tự chữ hoa của '%c' là '%c'\n", ch, upperCh);
    return 0;
}
```

### Ví dụ 2: Chuyển đổi chuỗi ký tự
```c
#include <stdio.h>
#include <ctype.h>

void convertToUpper(char str[]) {
    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = toupper(str[i]);
    }
}

int main() {
    char str[] = "hello world";
    convertToUpper(str);
    printf("Chuỗi chữ hoa: %s\n", str);
    return 0;
}
```

## Giải thích
Khi sử dụng hàm `toupper`, cần lưu ý một số điểm sau:
- **Ký tự không phải chữ cái**: Nếu bạn truyền vào một ký tự không phải là chữ cái (ví dụ: số hoặc ký tự đặc biệt), hàm sẽ trả về ký tự đó mà không thay đổi.
- **Giá trị không hợp lệ**: Hàm `toupper` có thể nhận các giá trị nguyên khác ngoài ký tự ASCII. Tuy nhiên, để đảm bảo tính chính xác, tốt nhất nên truyền vào các ký tự trong phạm vi ASCII.
- **Thư viện cần thiết**: Đảm bảo rằng bạn đã bao gồm thư viện `<ctype.h>` trước khi sử dụng hàm này.

## Tóm tắt một dòng
Hàm `toupper` trong C chuyển đổi ký tự chữ thường thành chữ hoa, giúp đơn giản hóa việc xử lý văn bản.