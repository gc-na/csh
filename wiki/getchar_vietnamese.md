<!--
Meta Description: # Hàm getchar trong ngôn ngữ lập trình C: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Hàm `getchar` trong ngôn ngữ lập trình C là một hàm tiêu chuẩn được s...
Meta Keywords: một, hàm, getchar, đọc, vào
-->

# Hàm getchar trong ngôn ngữ lập trình C: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Hàm `getchar` trong ngôn ngữ lập trình C là một hàm tiêu chuẩn được sử dụng để đọc một ký tự từ đầu vào chuẩn (thường là bàn phím). Hàm này trả về ký tự đầu tiên được nhập và có thể được sử dụng trong các ứng dụng tương tác với người dùng.

## Tài liệu
### Mục đích
Hàm `getchar` được sử dụng để đọc một ký tự từ đầu vào chuẩn. Đây là một công cụ đơn giản nhưng hữu ích cho việc thu thập thông tin từ người dùng trong các chương trình C.

### Cú pháp
```c
int getchar(void);
```

### Tham số
- Hàm `getchar` không nhận tham số nào.

### Trả về
- Hàm sẽ trả về ký tự được đọc nếu thành công. Nếu có lỗi xảy ra hoặc đạt đến EOF (End Of File), hàm sẽ trả về `EOF` (thường có giá trị -1).

### Chi tiết
- Khi hàm `getchar` được gọi, chương trình sẽ dừng lại và chờ người dùng nhập một ký tự.
- Hàm này là một phần của thư viện `<stdio.h>`, do đó cần phải bao gồm thư viện này trong chương trình của bạn.
- `getchar` là một hàm đồng bộ, nghĩa là nó sẽ chờ cho đến khi có dữ liệu đầu vào trước khi tiếp tục thực thi.

## Ví dụ
### Ví dụ 1: Đọc và in ra ký tự
```c
#include <stdio.h>

int main() {
    char c;
    printf("Nhập vào một ký tự: ");
    c = getchar();
    printf("Ký tự bạn đã nhập là: %c\n", c);
    return 0;
}
```

### Ví dụ 2: Đọc nhiều ký tự cho đến khi nhấn Enter
```c
#include <stdio.h>

int main() {
    char c;
    printf("Nhập vào một chuỗi ký tự (nhấn Enter để kết thúc): \n");
    while ((c = getchar()) != '\n') {
        putchar(c); // In ra ký tự đã nhập
    }
    return 0;
}
```

## Giải thích
- Một số người mới học có thể gặp khó khăn khi sử dụng `getchar` do không biết rằng hàm này chỉ đọc một ký tự tại một thời điểm. Điều này có thể dẫn đến việc bỏ qua các ký tự hoặc không nhận được toàn bộ chuỗi đầu vào.
- Cần lưu ý rằng `getchar` sẽ không tự động loại bỏ ký tự xuống dòng (`\n`) khi người dùng nhấn Enter. Nếu bạn cần xử lý chuỗi, hãy sử dụng một vòng lặp để đọc từng ký tự cho đến khi gặp dấu xuống dòng.
- Việc sử dụng `getchar` trong một vòng lặp có thể dẫn đến việc chương trình không hoạt động như mong đợi nếu không xử lý đúng các ký tự đầu vào.

## Tóm tắt một dòng
Hàm `getchar` trong C cho phép bạn đọc một ký tự từ đầu vào chuẩn, rất hữu ích cho việc tương tác với người dùng.