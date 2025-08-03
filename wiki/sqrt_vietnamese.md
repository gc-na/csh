<!--
Meta Description: # Hàm sqrt trong C: Tính căn bậc hai ## Tóm tắt Hàm `sqrt` trong ngôn ngữ lập trình C được sử dụng để tính căn bậc hai của một số thực. Đây là một hàm...
Meta Keywords: hàm, căn, bậc, hai, sqrt
-->

# Hàm sqrt trong C: Tính căn bậc hai

## Tóm tắt
Hàm `sqrt` trong ngôn ngữ lập trình C được sử dụng để tính căn bậc hai của một số thực. Đây là một hàm quan trọng trong các ứng dụng toán học và khoa học máy tính.

## Tài liệu
### Mục đích
Hàm `sqrt` được sử dụng để trả về căn bậc hai của một số. Nếu đầu vào là một số dương, hàm trả về giá trị căn bậc hai của số đó. Nếu đầu vào là số âm, hàm sẽ trả về giá trị không xác định (NaN).

### Cú pháp
```c
#include <math.h>

double sqrt(double x);
```

### Tham số
- `x`: Một số thực không âm mà bạn muốn tính căn bậc hai.

### Giá trị trả về
- Trả về giá trị căn bậc hai của `x` nếu `x` không âm.
- Trả về giá trị không xác định (NaN) nếu `x` âm.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng hàm `sqrt`.

### Ví dụ 1: Tính căn bậc hai của số dương
```c
#include <stdio.h>
#include <math.h>

int main() {
    double number = 16.0;
    double result = sqrt(number);
    printf("Căn bậc hai của %.2f là %.2f\n", number, result);
    return 0;
}
```

### Ví dụ 2: Tính căn bậc hai của số âm
```c
#include <stdio.h>
#include <math.h>

int main() {
    double number = -9.0;
    double result = sqrt(number);
    printf("Căn bậc hai của %.2f là %.2f\n", number, result);
    return 0;
}
```

## Giải thích
- **Lưu ý về tham số âm**: Khi truyền một số âm vào hàm `sqrt`, bạn sẽ nhận được giá trị không xác định (NaN). Để tránh điều này, hãy đảm bảo rằng giá trị đầu vào luôn không âm.
- **Thư viện math.h**: Để sử dụng hàm `sqrt`, bạn cần bao gồm thư viện `math.h` trong chương trình của mình.
- **Kiểm tra giá trị trả về**: Đôi khi, bạn có thể muốn kiểm tra xem giá trị trả về có phải là NaN hay không. Bạn có thể sử dụng hàm `isnan()` để thực hiện việc này.

## Tóm tắt một dòng
Hàm `sqrt` trong C tính căn bậc hai của một số thực không âm và trả về NaN nếu đầu vào là số âm.