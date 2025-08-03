<!--
Meta Description: # Hàm floor trong ngôn ngữ lập trình C: Cách sử dụng và ứng dụng ## Tóm tắt Hàm `floor` trong C là một hàm toán học được sử dụng để làm tròn một số th...
Meta Keywords: floor, hàm, giá, trị, làm
-->

# Hàm floor trong ngôn ngữ lập trình C: Cách sử dụng và ứng dụng

## Tóm tắt
Hàm `floor` trong C là một hàm toán học được sử dụng để làm tròn một số thực xuống số nguyên gần nhất mà không vượt quá giá trị của nó. 

## Tài liệu
Hàm `floor` được định nghĩa trong thư viện `<math.h>`. Mục đích của hàm này là lấy giá trị lớn nhất không vượt quá giá trị đầu vào. Cú pháp của hàm như sau:

```c
double floor(double x);
```

### Tham số
- `x`: Là số thực mà bạn muốn làm tròn xuống.

### Giá trị trả về
Hàm `floor` trả về giá trị kiểu `double`, là giá trị của `x` được làm tròn xuống số nguyên gần nhất.

### Lưu ý
- Hàm `floor` có thể xử lý các số âm. Trong trường hợp này, nó sẽ trả về giá trị số nguyên lớn nhất không lớn hơn số thực đầu vào.
- Kết quả của hàm `floor` sẽ không thay đổi nếu giá trị đầu vào đã là một số nguyên.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng hàm `floor`:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num1 = 3.7;
    double num2 = -2.3;
    double num3 = 5.0;

    printf("floor(%.1f) = %.1f\n", num1, floor(num1)); // Kết quả: 3.0
    printf("floor(%.1f) = %.1f\n", num2, floor(num2)); // Kết quả: -3.0
    printf("floor(%.1f) = %.1f\n", num3, floor(num3)); // Kết quả: 5.0

    return 0;
}
```

## Giải thích
- Một số lập trình viên có thể nhầm lẫn giữa hàm `floor` và các hàm làm tròn khác như `ceil` (làm tròn lên) và `round` (làm tròn theo quy tắc số học). Cần lưu ý rằng `floor` luôn làm tròn xuống, bất kể giá trị của phần thập phân.
- Khi làm việc với số âm, giá trị trả về của hàm `floor` có thể gây bất ngờ, vì nó sẽ trả về số nguyên lớn hơn gần nhất (ví dụ: `floor(-2.3)` sẽ là `-3.0`).

## Tóm tắt một dòng
Hàm `floor` trong C là công cụ hữu ích để làm tròn một số thực xuống số nguyên gần nhất mà không vượt quá giá trị của nó.