<!--
Meta Description: # Hàm cos trong C: Tính toán Cosine một cách chính xác ## Tóm tắt Hàm `cos` trong ngôn ngữ lập trình C là một hàm toán học dùng để tính giá trị cosine...
Meta Keywords: hàm, cos, tính, giá, trị
-->

# Hàm cos trong C: Tính toán Cosine một cách chính xác

## Tóm tắt
Hàm `cos` trong ngôn ngữ lập trình C là một hàm toán học dùng để tính giá trị cosine của một góc được cung cấp dưới dạng radian. Hàm này được định nghĩa trong thư viện `<math.h>` và thường được sử dụng trong các ứng dụng cần tính toán liên quan đến hình học và vật lý.

## Tài liệu
Hàm `cos` tính toán giá trị cosine của một số thực. Để sử dụng hàm này, bạn cần bao gồm thư viện `<math.h>`. Hàm có cú pháp như sau:

```c
double cos(double x);
```

### Mục đích
- Tính giá trị cosine của góc x (được tính bằng radian).

### Tham số
- `x`: Góc tính bằng radian. Ví dụ, 0 radian tương ứng với 0 độ, và π radian tương ứng với 180 độ.

### Trả về
- Hàm trả về giá trị cosine của góc x dưới dạng kiểu `double`. Giá trị trả về nằm trong khoảng từ -1 đến 1.

### Lưu ý
- Nếu giá trị đầu vào là NaN (Not a Number), hàm sẽ trả về NaN.
- Nếu giá trị đầu vào là vô cực, hàm sẽ trả về NaN.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng hàm `cos` trong C:

### Ví dụ 1: Tính giá trị cosine của 0 radian
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = 0.0;
    double result = cos(angle);
    printf("cos(%.2f) = %.2f\n", angle, result);
    return 0;
}
```

### Ví dụ 2: Tính giá trị cosine của π/2 radian
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 2; // π/2 radian
    double result = cos(angle);
    printf("cos(%.2f) = %.2f\n", angle, result);
    return 0;
}
```

### Ví dụ 3: Tính giá trị cosine của góc âm
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = -M_PI; // -π radian
    double result = cos(angle);
    printf("cos(%.2f) = %.2f\n", angle, result);
    return 0;
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng hàm `cos`:
- Đảm bảo rằng bạn chuyển đổi góc từ độ sang radian nếu cần. Bạn có thể sử dụng công thức: `radian = độ * (π / 180)`.
- Kiểm tra giá trị trả về để xử lý các trường hợp NaN hoặc vô cực, nhằm tránh các lỗi không mong muốn trong chương trình.
- Hàm `cos` có thể tích hợp với các hàm toán học khác trong `<math.h>`, như `sin` (tính sin) và `tan` (tính tan), để thực hiện các tính toán phức tạp hơn.

## Tóm tắt một câu
Hàm `cos` trong C được sử dụng để tính giá trị cosine của một góc được cung cấp bằng radian, hỗ trợ trong nhiều ứng dụng toán học và khoa học.