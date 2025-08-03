<!--
Meta Description: # C Switch: Câu lệnh Chuyển Nhánh trong Ngôn Ngữ Lập Trình C ## Tóm tắt Câu lệnh `switch` trong ngôn ngữ lập trình C cho phép người lập trình thực hiệ...
Meta Keywords: lệnh, switch, case, câu, biến
-->

# C Switch: Câu lệnh Chuyển Nhánh trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Câu lệnh `switch` trong ngôn ngữ lập trình C cho phép người lập trình thực hiện các lựa chọn khác nhau dựa trên giá trị của một biến, giúp mã nguồn trở nên dễ đọc và bảo trì hơn.

## Tài liệu
Câu lệnh `switch` được sử dụng để thực hiện lựa chọn đa nhánh trong C. Cú pháp cơ bản của câu lệnh `switch` như sau:

```c
switch (biến) {
    case giá_trị1:
        // Khối lệnh khi biến bằng giá_trị1
        break;
    case giá_trị2:
        // Khối lệnh khi biến bằng giá_trị2
        break;
    // Các case khác
    default:
        // Khối lệnh khi không khớp với bất kỳ case nào
}
```

### Mục đích
Câu lệnh `switch` giúp xử lý nhiều trường hợp khác nhau dựa trên giá trị của một biểu thức. Điều này có thể thay thế cho nhiều câu lệnh `if-else`, giúp mã nguồn ngắn gọn và dễ hiểu hơn.

### Cách sử dụng
- **Biến trong switch**: Biến có thể là kiểu nguyên thủy như `int`, `char`, hoặc `enum`.
- **Các case**: Mỗi `case` xác định một giá trị mà biến có thể nhận. 
- **Khối lệnh**: Các khối lệnh cho từng `case` sẽ được thực hiện nếu giá trị của biến khớp với giá trị của `case`. 
- **Câu lệnh `break`**: Dùng để thoát khỏi câu lệnh `switch`. Nếu thiếu `break`, chương trình sẽ tiếp tục thực thi các `case` tiếp theo cho đến khi gặp `break` hoặc kết thúc `switch`.
- **`default`**: Là trường hợp mặc định, được thực hiện khi không có `case` nào khớp. Nó là tùy chọn nhưng rất hữu ích để xử lý các giá trị không mong muốn.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng câu lệnh `switch`:

```c
#include <stdio.h>

int main() {
    int ngay = 3;

    switch (ngay) {
        case 1:
            printf("Thứ Hai\n");
            break;
        case 2:
            printf("Thứ Ba\n");
            break;
        case 3:
            printf("Thứ Tư\n");
            break;
        default:
            printf("Ngày không hợp lệ\n");
    }

    return 0;
}
```

Kết quả của chương trình này sẽ là:
```
Thứ Tư
```

## Giải thích
Một số vấn đề thường gặp khi sử dụng câu lệnh `switch`:

- **Thiếu `break`**: Nếu bạn quên câu lệnh `break`, chương trình sẽ tiếp tục thực thi các `case` sau đó, điều này có thể dẫn đến kết quả không mong muốn.
- **Kiểu dữ liệu không hợp lệ**: Biến trong `switch` phải là kiểu dữ liệu nguyên thủy như `int` hoặc `char`. Câu lệnh `switch` không hỗ trợ kiểu dữ liệu như `float` hay `double`.
- **Giá trị trùng lặp**: Không thể có hai hoặc nhiều `case` với cùng một giá trị. Điều này sẽ gây ra lỗi biên dịch.

## Tóm tắt một dòng
Câu lệnh `switch` trong C cho phép thực hiện lựa chọn đa nhánh dựa trên giá trị của một biến, giúp mã nguồn gọn gàng và dễ bảo trì.