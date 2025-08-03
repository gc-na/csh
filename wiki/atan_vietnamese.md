<!--
Meta Description: # Hàm atan trong C - Tính toán góc của đối số ## Tóm tắt Hàm `atan` trong ngôn ngữ lập trình C được sử dụng để tính toán arctangent (góc đối diện) của...
Meta Keywords: trong, hàm, atan, của, radian
-->

# Hàm atan trong C - Tính toán góc của đối số

## Tóm tắt
Hàm `atan` trong ngôn ngữ lập trình C được sử dụng để tính toán arctangent (góc đối diện) của một số thực. Hàm này thường được sử dụng trong các bài toán liên quan đến hình học, vật lý, và kỹ thuật.

## Tài liệu
### Mục đích
Hàm `atan` trả về góc (đơn vị radian) mà có tangent bằng một giá trị cho trước. Nó là phần của thư viện toán học trong C, được định nghĩa trong `<math.h>`.

### Cú pháp
```c
#include <math.h>

double atan(double x);
```

### Tham số
- `x`: Một số thực mà bạn muốn tính arctangent.

### Giá trị trả về
- Hàm trả về góc (đơn vị radian) trong khoảng từ `-π/2` đến `π/2`.

## Ví dụ
### Ví dụ cơ bản
```c
#include <stdio.h>
#include <math.h>

int main() {
    double value = 1.0;
    double result = atan(value);
    
    printf("Arctangent của %.2f là: %.2f radian\n", value, result);
    return 0;
}
```

### Ví dụ với nhiều giá trị
```c
#include <stdio.h>
#include <math.h>

int main() {
    double values[] = {0.0, 1.0, -1.0, 0.5, -0.5};
    for (int i = 0; i < 5; i++) {
        printf("Arctangent của %.2f là: %.2f radian\n", values[i], atan(values[i]));
    }
    return 0;
}
```

## Giải thích
- **Lưu ý về đơn vị**: Kết quả của hàm `atan` là góc được biểu diễn bằng radian, không phải độ. Để chuyển đổi sang độ, bạn có thể sử dụng công thức: `độ = radian * (180/π)`.
- **Giá trị đầu vào**: Hàm `atan` có thể nhận bất kỳ giá trị thực nào, bao gồm số dương, số âm, và cả 0.
- **Giới hạn giá trị trả về**: Kết quả của hàm sẽ luôn nằm trong khoảng từ `-π/2` đến `π/2`, điều này có thể gây nhầm lẫn nếu bạn mong đợi giá trị ra ngoài khoảng này.

## Tóm tắt một dòng
Hàm `atan` trong C tính toán arctangent của một số thực, trả về góc trong radian trong khoảng từ `-π/2` đến `π/2`.