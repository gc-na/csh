<!--
Meta Description: # Lệnh "case" trong ngôn ngữ lập trình C: Hướng dẫn và Ví dụ ## Tóm tắt Lệnh `case` trong ngôn ngữ lập trình C cho phép lập trình viên thực hiện lựa c...
Meta Keywords: case, giá, trị, biến, trong
-->

# Lệnh "case" trong ngôn ngữ lập trình C: Hướng dẫn và Ví dụ

## Tóm tắt
Lệnh `case` trong ngôn ngữ lập trình C cho phép lập trình viên thực hiện lựa chọn giữa nhiều giá trị khác nhau của một biến trong cấu trúc điều kiện `switch`, giúp code trở nên gọn gàng và dễ đọc hơn.

## Tài liệu
### Mục đích
Lệnh `case` được sử dụng trong cấu trúc `switch` để kiểm tra giá trị của một biến. Khi giá trị của biến khớp với một giá trị `case`, đoạn mã tương ứng với giá trị đó sẽ được thực thi.

### Cú pháp
Cú pháp cơ bản của lệnh `case` trong cấu trúc `switch` như sau:

```c
switch (biến) {
    case giá_trị_1:
        // đoạn mã thực thi khi biến == giá_trị_1
        break;
    case giá_trị_2:
        // đoạn mã thực thi khi biến == giá_trị_2
        break;
    // Thêm nhiều case nếu cần
    default:
        // đoạn mã thực thi khi không khớp với bất kỳ giá trị nào
}
```

### Chi tiết
- **biến**: Là biến mà bạn muốn kiểm tra giá trị.
- **giá_trị**: Là các giá trị mà biến có thể khớp với nhau.
- **break**: Dùng để ngăn việc tiếp tục thực thi các case sau khi đã tìm thấy case khớp. Nếu không có `break`, chương trình sẽ tiếp tục thực thi các case tiếp theo cho đến khi gặp `break` hoặc kết thúc switch.
- **default**: Là tùy chọn, được sử dụng để xử lý trường hợp khi không có giá trị nào khớp với biến.

## Ví dụ
### Ví dụ 1: Cấu trúc điều kiện đơn giản
```c
#include <stdio.h>

int main() {
    int x = 2;
    switch (x) {
        case 1:
            printf("Giá trị là 1\n");
            break;
        case 2:
            printf("Giá trị là 2\n");
            break;
        default:
            printf("Giá trị không khớp\n");
    }
    return 0;
}
```

### Ví dụ 2: Sử dụng nhiều case
```c
#include <stdio.h>

int main() {
    char grade = 'B';
    switch (grade) {
        case 'A':
        case 'B':
        case 'C':
            printf("Bạn đã đạt yêu cầu\n");
            break;
        case 'D':
        case 'F':
            printf("Bạn cần cải thiện\n");
            break;
        default:
            printf("Điểm không hợp lệ\n");
    }
    return 0;
}
```

## Giải thích
- **Các cạm bẫy thường gặp**: Một trong những điều cần lưu ý khi sử dụng lệnh `case` là quên thêm lệnh `break`, điều này có thể dẫn đến việc thực thi không mong muốn. 
- **Giá trị không khớp**: Nếu không có giá trị nào khớp, chương trình sẽ thực thi đoạn mã trong `default`, nếu có.
- **Giá trị của case**: Các giá trị trong case phải là hằng số, không thể là biến hoặc biểu thức.

## Tóm tắt một dòng
Lệnh `case` trong C cho phép lựa chọn giữa nhiều giá trị của một biến trong cấu trúc `switch`, giúp lập trình viên tổ chức mã nguồn một cách hiệu quả và dễ hiểu.