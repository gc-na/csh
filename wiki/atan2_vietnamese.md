<!--
Meta Description: # Hàm atan2 trong C: Tính toán góc từ tọa độ Cartesian ## Tóm tắt Hàm `atan2` trong ngôn ngữ lập trình C được sử dụng để tính toán góc (đơn vị radian)...
Meta Keywords: góc, atan2, trong, hàm, double
-->

# Hàm atan2 trong C: Tính toán góc từ tọa độ Cartesian

## Tóm tắt
Hàm `atan2` trong ngôn ngữ lập trình C được sử dụng để tính toán góc (đơn vị radian) giữa trục hoành và đoạn thẳng nối điểm gốc với một điểm có tọa độ (x, y) trong hệ tọa độ Cartesian. Hàm này giúp xác định góc một cách chính xác trong toàn bộ không gian hai chiều.

## Tài liệu
### Mục đích
Hàm `atan2` cho phép lập trình viên dễ dàng tính toán góc cho các ứng dụng liên quan đến toán học, đồ họa máy tính, và robot. Hàm này xử lý các trường hợp đặc biệt mà hàm `atan` không thể, như điểm trên trục hoành và trục tung.

### Cú pháp
```c
double atan2(double y, double x);
```

### Tham số
- `y`: Giá trị tọa độ y của điểm.
- `x`: Giá trị tọa độ x của điểm.

### Giá trị trả về
Hàm `atan2` trả về một giá trị kiểu `double`, đại diện cho góc (tính bằng radian) trong khoảng từ -π đến π.

### Chi tiết
Khi sử dụng `atan2`, hàm sẽ xác định góc dựa trên vị trí của (x, y) trong bốn góc của hệ tọa độ:
- Nếu `x` > 0, góc nằm trong khoảng [−π/2, π/2].
- Nếu `x` < 0, góc nằm trong khoảng [π/2, −π/2].
- Nếu `x` = 0 và `y` > 0, góc là π/2.
- Nếu `x` = 0 và `y` < 0, góc là −π/2.
- Nếu `x` = 0 và `y` = 0, hàm không xác định và thường dẫn đến lỗi.

## Ví dụ
### Ví dụ cơ bản
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 1.0, y = 1.0;
    double angle = atan2(y, x);

    printf("Góc (radian): %f\n", angle);
    printf("Góc (độ): %f\n", angle * (180.0 / M_PI)); // Chuyển đổi sang độ
    return 0;
}
```

### Ví dụ với các tọa độ khác
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x1 = 0.0, y1 = 1.0; // Góc π/2
    double x2 = -1.0, y2 = 0.0; // Góc π
    double x3 = 0.0, y3 = -1.0; // Góc -π/2
    double x4 = 1.0, y4 = -1.0; // Góc -π/4

    printf("Góc (π/2): %f\n", atan2(y1, x1));
    printf("Góc (π): %f\n", atan2(y2, x2));
    printf("Góc (-π/2): %f\n", atan2(y3, x3));
    printf("Góc (-π/4): %f\n", atan2(y4, x4));

    return 0;
}
```

## Giải thích
### Điểm cần lưu ý
- Khi sử dụng `atan2`, cần đảm bảo rằng tham số `x` và `y` không đồng thời bằng 0 để tránh lỗi không xác định.
- Hàm `atan2` giúp phân biệt các góc theo hướng của điểm (x, y), điều này rất hữu ích trong các ứng dụng cần xác định hướng hoặc vị trí trên mặt phẳng.

### Các lưu ý khác
- Kết quả của `atan2` là một giá trị `double`, do đó có thể cần được chuyển đổi nếu cần thiết (ví dụ: chuyển đổi sang độ).
- Hàm này có thể được sử dụng trong các bài toán về đồ họa máy tính, vật lý, cũng như trong các thuật toán điều khiển cho robot.

## Tóm tắt một dòng
Hàm `atan2` trong C tính toán góc giữa trục hoành và đoạn thẳng nối điểm gốc với điểm (x, y) trong hệ tọa độ Cartesian, với giá trị trả về là radian.