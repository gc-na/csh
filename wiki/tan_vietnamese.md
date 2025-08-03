<!--
Meta Description: # Hàm tan trong C - Tính toán hàm tang ## Tóm tắt Hàm `tan` trong ngôn ngữ lập trình C được sử dụng để tính giá trị tang của một góc cho trước, được b...
Meta Keywords: tính, giá, trị, hàm, tan
-->

# Hàm tan trong C - Tính toán hàm tang

## Tóm tắt
Hàm `tan` trong ngôn ngữ lập trình C được sử dụng để tính giá trị tang của một góc cho trước, được biểu diễn bằng radian. Hàm này nằm trong thư viện toán học `math.h`, và là một phần quan trọng trong các phép toán hình học và phân tích.

## Tài liệu
### Mục đích
Hàm `tan` giúp lập trình viên tính toán giá trị tang của một góc, thường được sử dụng trong các ứng dụng liên quan đến đồ họa máy tính, vật lý, và kỹ thuật.

### Cú pháp
```c
#include <math.h>

double tan(double x);
```

### Tham số
- `x`: Góc tính bằng radian mà bạn muốn tính giá trị tang.

### Giá trị trả về
Hàm `tan` trả về giá trị tang của góc `x`. Nếu `x` là một số không xác định như π/2 + kπ (với k là số nguyên), hàm sẽ trả về giá trị không xác định (NaN).

### Các yêu cầu
- Để sử dụng hàm `tan`, bạn phải bao gồm thư viện `math.h`.
- Đảm bảo rằng chương trình được biên dịch với tùy chọn liên kết đến thư viện toán học (`-lm` với GCC).

## Ví dụ
### Ví dụ 1: Tính giá trị tang của 45 độ
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 4; // 45 độ
    double result = tan(angle);
    printf("Tang của 45 độ là: %f\n", result);
    return 0;
}
```

### Ví dụ 2: Tính giá trị tang của 90 độ
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 2; // 90 độ
    double result = tan(angle);
    printf("Tang của 90 độ là: %f\n", result);
    return 0;
}
```

## Giải thích
- **Góc tính bằng radian**: Lưu ý rằng hàm `tan` chỉ chấp nhận giá trị góc được tính bằng radian, không phải độ. Để chuyển đổi độ sang radian, bạn có thể sử dụng công thức: `radian = độ * (π / 180)`.
  
- **Giá trị không xác định (NaN)**: Khi tính tang của các góc như π/2 (90 độ), hàm sẽ trả về giá trị không xác định. Điều này cần được xử lý cẩn thận trong mã nguồn để tránh lỗi tính toán.

- **Biên dịch với thư viện toán học**: Khi biên dịch chương trình sử dụng hàm `tan`, hãy nhớ thêm `-lm` vào dòng lệnh biên dịch nếu bạn sử dụng GCC, ví dụ: `gcc program.c -o program -lm`.

## Tóm tắt một dòng
Hàm `tan` trong C tính giá trị tang của góc cho trước, yêu cầu tham số là radian và có thể gây ra giá trị không xác định cho các góc đặc biệt.