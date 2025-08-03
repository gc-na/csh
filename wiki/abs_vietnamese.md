<!--
Meta Description: # Hàm abs trong C: Cách sử dụng và các lưu ý ## Tóm tắt Hàm `abs` trong C được sử dụng để tính giá trị tuyệt đối của một số nguyên. Đây là một hàm tiê...
Meta Keywords: hàm, giá, trị, abs, dụng
-->

# Hàm abs trong C: Cách sử dụng và các lưu ý

## Tóm tắt
Hàm `abs` trong C được sử dụng để tính giá trị tuyệt đối của một số nguyên. Đây là một hàm tiêu chuẩn trong thư viện `<stdlib.h>` và rất hữu ích trong nhiều tình huống lập trình.

## Tài liệu
Hàm `abs` có mục đích chính là trả về giá trị tuyệt đối của một số nguyên. Cú pháp của hàm như sau:

```c
#include <stdlib.h>

int abs(int x);
```

### Tham số
- `x`: Là số nguyên mà bạn muốn tính giá trị tuyệt đối.

### Giá trị trả về
Hàm sẽ trả về một số nguyên dương tương ứng với giá trị tuyệt đối của `x`. Nếu `x` là số âm, hàm sẽ trả về giá trị dương tương ứng. Nếu `x` bằng 0, hàm sẽ trả về 0.

### Lưu ý
- Hàm `abs` chỉ hoạt động với kiểu dữ liệu `int`. Nếu bạn cần tính giá trị tuyệt đối cho các kiểu số khác như `float` hoặc `double`, bạn nên sử dụng các hàm tương đương như `fabs` hoặc `fabsl`.

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng hàm `abs` trong C:

### Ví dụ 1: Sử dụng với số dương
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num = 5;
    printf("Giá trị tuyệt đối của %d là: %d\n", num, abs(num));
    return 0;
}
```

### Ví dụ 2: Sử dụng với số âm
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num = -10;
    printf("Giá trị tuyệt đối của %d là: %d\n", num, abs(num));
    return 0;
}
```

### Ví dụ 3: Sử dụng với 0
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num = 0;
    printf("Giá trị tuyệt đối của %d là: %d\n", num, abs(num));
    return 0;
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng hàm `abs`:
- Nếu bạn đưa vào giá trị `INT_MIN` (giá trị nhỏ nhất của kiểu int), giá trị trả về sẽ không chính xác do tràn số. Điều này là một điều cần tránh trong lập trình.
- Luôn đảm bảo rằng bạn đã bao gồm thư viện `<stdlib.h>` để sử dụng hàm này.
- Đối với số thực, sử dụng `fabs` thay vì `abs` để tránh các vấn đề về kiểu dữ liệu.

## Tóm tắt một dòng
Hàm `abs` trong C là công cụ đơn giản nhưng mạnh mẽ để tính giá trị tuyệt đối của số nguyên.