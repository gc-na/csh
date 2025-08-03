<!--
Meta Description: # Hàm sin trong C: Tính toán giá trị sin của một góc ## Tóm tắt Hàm `sin` trong ngôn ngữ lập trình C được sử dụng để tính giá trị sin của một góc được...
Meta Keywords: sin, một, của, hàm, tính
-->

# Hàm sin trong C: Tính toán giá trị sin của một góc

## Tóm tắt
Hàm `sin` trong ngôn ngữ lập trình C được sử dụng để tính giá trị sin của một góc được biểu diễn bằng radian. Hàm này là một phần của thư viện toán học chuẩn `<math.h>`.

## Tài liệu
### Mục đích
Hàm `sin` tính toán giá trị sin của một góc, được cung cấp dưới dạng một số thực có kiểu `double`. Kết quả trả về cũng là một số thực có kiểu `double`.

### Cú pháp
```c
#include <math.h>

double sin(double x);
```

### Tham số
- `x`: Góc tính bằng radian mà bạn muốn tính giá trị sin.

### Giá trị trả về
- Hàm trả về giá trị sin của góc `x`. Kết quả sẽ nằm trong khoảng từ -1 đến 1.

### Lưu ý
- Để sử dụng hàm `sin`, bạn cần phải bao gồm thư viện `<math.h>` trong mã nguồn của mình.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng hàm `sin`:

### Ví dụ 1: Tính sin của 0
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = 0.0;
    printf("sin(%.2f) = %.2f\n", angle, sin(angle));
    return 0;
}
```

### Ví dụ 2: Tính sin của pi/2
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 2; // M_PI là hằng số pi
    printf("sin(%.2f) = %.2f\n", angle, sin(angle));
    return 0;
}
```

### Ví dụ 3: Tính sin của một góc âm
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = -M_PI / 4; // -pi/4
    printf("sin(%.2f) = %.2f\n", angle, sin(angle));
    return 0;
}
```

## Giải thích
Khi làm việc với hàm `sin`, có một số điều bạn cần lưu ý:
- **Đơn vị:** Hàm `sin` sử dụng radian, không phải độ. Nếu bạn có một góc trong độ, bạn cần chuyển đổi nó sang radian bằng cách sử dụng công thức: `radian = degree * (M_PI / 180)`.
- **Thư viện toán học:** Đảm bảo rằng bạn đã liên kết với thư viện toán học khi biên dịch bằng cách sử dụng cờ `-lm` (ví dụ: `gcc -o my_program my_program.c -lm`).
- **Giá trị trả về:** Kết quả của hàm `sin` có thể có giá trị gần bằng 1 hoặc -1 cho các góc đặc biệt (như 90 độ hoặc -90 độ), nhưng không bao giờ vượt quá khoảng [-1, 1].

## Tóm tắt một câu
Hàm `sin` trong C được sử dụng để tính giá trị sin của một góc, được biểu diễn bằng radian, và là một phần quan trọng của thư viện toán học chuẩn.