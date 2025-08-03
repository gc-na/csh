<!--
Meta Description: # Câu lệnh "if" trong ngôn ngữ lập trình C: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Câu lệnh "if" trong ngôn ngữ lập trình C là một cấu trúc điều kiện ...
Meta Keywords: lệnh, câu, điều, thực, else
-->

# Câu lệnh "if" trong ngôn ngữ lập trình C: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Câu lệnh "if" trong ngôn ngữ lập trình C là một cấu trúc điều kiện cho phép lập trình viên kiểm tra và thực hiện các đoạn mã khác nhau dựa trên kết quả của một biểu thức điều kiện.

## Tài liệu
Câu lệnh "if" được sử dụng để thực hiện các quyết định trong chương trình. Cú pháp cơ bản của câu lệnh "if" như sau:

```c
if (biểu_thức) {
    // Khối mã thực thi nếu biểu thức đúng
}
```

- **Mục đích**: Câu lệnh "if" cho phép chương trình xác định xem một điều kiện có đúng hay không và thực hiện các hành động tương ứng.
- **Sử dụng**: Bạn có thể sử dụng câu lệnh "if" đơn giản hoặc kết hợp với các câu lệnh "else" hoặc "else if" để xử lý nhiều điều kiện.

Cú pháp mở rộng cho câu lệnh "if" có thể như sau:

```c
if (biểu_thức_1) {
    // Khối mã thực thi nếu biểu thức_1 đúng
} else if (biểu_thức_2) {
    // Khối mã thực thi nếu biểu thức_2 đúng
} else {
    // Khối mã thực thi nếu không có biểu thức nào đúng
}
```

## Ví dụ
Dưới đây là một số ví dụ đơn giản sử dụng câu lệnh "if":

### Ví dụ 1: Câu lệnh "if" cơ bản
```c
#include <stdio.h>

int main() {
    int a = 10;
    if (a > 5) {
        printf("a lớn hơn 5\n");
    }
    return 0;
}
```

### Ví dụ 2: Câu lệnh "if" với "else"
```c
#include <stdio.h>

int main() {
    int b = 3;
    if (b > 5) {
        printf("b lớn hơn 5\n");
    } else {
        printf("b không lớn hơn 5\n");
    }
    return 0;
}
```

### Ví dụ 3: Sử dụng "else if"
```c
#include <stdio.h>

int main() {
    int c = 5;
    if (c > 5) {
        printf("c lớn hơn 5\n");
    } else if (c == 5) {
        printf("c bằng 5\n");
    } else {
        printf("c nhỏ hơn 5\n");
    }
    return 0;
}
```

## Giải thích
Một số vấn đề thường gặp khi sử dụng câu lệnh "if":

- **Không dùng dấu ngoặc nhọn**: Nếu chỉ có một lệnh trong khối "if", bạn có thể bỏ qua dấu ngoặc nhọn. Tuy nhiên, điều này có thể gây nhầm lẫn khi bạn muốn thêm lệnh sau này.
- **Biểu thức điều kiện**: Cần chú ý rằng bất kỳ giá trị nào khác 0 đều được coi là "đúng" (true) và 0 là "sai" (false).
- **Giá trị không mong muốn**: Đảm bảo rằng bạn kiểm tra các điều kiện đúng cách để tránh các kết quả không mong muốn trong chương trình.

## Tóm tắt một dòng
Câu lệnh "if" trong C cho phép lập trình viên thực hiện các quyết định dựa trên các điều kiện, giúp điều khiển luồng thực thi của chương trình.