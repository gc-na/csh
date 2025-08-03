<!--
Meta Description: # Hàm log10 trong C: Tính Logarit Cơ Số 10 ## Tóm tắt Hàm `log10` trong ngôn ngữ lập trình C được sử dụng để tính toán logarit cơ số 10 của một số thự...
Meta Keywords: hàm, log10, logarit, trong, một
-->

# Hàm log10 trong C: Tính Logarit Cơ Số 10

## Tóm tắt
Hàm `log10` trong ngôn ngữ lập trình C được sử dụng để tính toán logarit cơ số 10 của một số thực. Hàm này là một phần của thư viện toán học `math.h` và rất hữu ích trong các ứng dụng khoa học và kỹ thuật.

## Tài liệu
Hàm `log10` có cú pháp như sau:

```c
#include <math.h>

double log10(double x);
```

### Mục đích
Hàm `log10` trả về logarit cơ số 10 của tham số `x`. Nếu `x` là một số âm hoặc bằng 0, hàm sẽ trả về giá trị không xác định (NaN).

### Tham số
- `x`: Một số thực (double) mà bạn muốn tính logarit cơ số 10.

### Giá trị trả về
- Nếu `x` lớn hơn 0, hàm trả về logarit cơ số 10 của `x`.
- Nếu `x` <= 0, hàm trả về NaN (Not a Number).

### Lưu ý
Để sử dụng hàm này, bạn cần bao gồm thư viện `math.h` trong chương trình của mình.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng hàm `log10` trong C:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num1 = 100.0;
    double num2 = 0.001;
    double num3 = -10.0;

    printf("log10(%.2f) = %.2f\n", num1, log10(num1)); // Kết quả: 2.00
    printf("log10(%.2f) = %.2f\n", num2, log10(num2)); // Kết quả: -3.00
    printf("log10(%.2f) = %.2f\n", num3, log10(num3)); // Kết quả: NaN

    return 0;
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng hàm `log10`:
- Hàm này không thể tính logarit cho các số âm hoặc 0. Nếu bạn cố gắng truyền vào giá trị này, kết quả sẽ là NaN. Hãy luôn kiểm tra giá trị đầu vào trước khi gọi hàm để tránh lỗi không mong muốn.
- Hàm `log10` thường được sử dụng trong các ứng dụng khoa học, thống kê và tài chính để xử lý dữ liệu logarit, vì logarit cơ số 10 thường xuất hiện trong nhiều lĩnh vực.

## Tóm tắt một dòng
Hàm `log10` trong C tính toán logarit cơ số 10 của một số thực, trả về NaN cho các giá trị không hợp lệ.