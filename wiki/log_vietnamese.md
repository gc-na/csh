<!--
Meta Description: # Hàm log trong C: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Hàm `log` trong ngôn ngữ lập trình C được sử dụng để tính logarithm tự nhiên (logarit cơ số ...
Meta Keywords: log, hàm, dụng, của, trong
-->

# Hàm log trong C: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Hàm `log` trong ngôn ngữ lập trình C được sử dụng để tính logarithm tự nhiên (logarit cơ số e) của một số. Hàm này rất hữu ích trong các ứng dụng khoa học, kỹ thuật và tài chính.

## Tài liệu
Hàm `log` được định nghĩa trong thư viện `<math.h>`. Nó nhận một số thực dương và trả về logarithm tự nhiên của số đó. Cú pháp của hàm như sau:

```c
#include <math.h>

double log(double x);
```

### Mục đích
Hàm `log` được sử dụng để tính giá trị logarithm tự nhiên, giúp thực hiện các phép toán liên quan đến logarit trong các ứng dụng khác nhau.

### Sử dụng
- **Tham số**: Hàm nhận một tham số `x` là số thực dương mà ta muốn tính logarithm tự nhiên.
- **Trả về**: Trả về giá trị logarithm tự nhiên của `x`. Nếu `x` nhỏ hơn hoặc bằng 0, hàm sẽ trả về giá trị NaN (Not a Number).

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng hàm `log` trong C:

### Ví dụ 1: Tính log của một số
```c
#include <stdio.h>
#include <math.h>

int main() {
    double number = 2.71828; // Gần đúng với e
    double result = log(number);
    printf("log(%.5f) = %.5f\n", number, result);
    return 0;
}
```

### Ví dụ 2: Tính log của số 10
```c
#include <stdio.h>
#include <math.h>

int main() {
    double number = 10.0;
    double result = log(number);
    printf("log(%.2f) = %.5f\n", number, result);
    return 0;
}
```

## Giải thích
Khi sử dụng hàm `log`, cần lưu ý một số điểm sau:
- **Giá trị âm**: Hàm `log` không thể tính cho các giá trị âm hoặc 0. Nếu truyền vào giá trị này, chương trình có thể trả về NaN hoặc gây ra lỗi.
- **Độ chính xác**: Kết quả của hàm `log` phụ thuộc vào độ chính xác của kiểu dữ liệu `double`. Đối với các giá trị rất lớn hoặc rất nhỏ, có thể cần kiểm tra lại kết quả để đảm bảo tính chính xác.

## Tóm tắt một dòng
Hàm `log` trong C được sử dụng để tính logarithm tự nhiên của một số thực dương, rất hữu ích trong các ứng dụng khoa học và kỹ thuật.