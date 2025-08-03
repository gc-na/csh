<!--
Meta Description: # Hàm rand() trong C: Tạo số ngẫu nhiên hiệu quả ## Tóm tắt Hàm `rand()` trong ngôn ngữ lập trình C là một công cụ quan trọng để sinh số ngẫu nhiên. N...
Meta Keywords: ngẫu, nhiên, rand, hàm, trong
-->

# Hàm rand() trong C: Tạo số ngẫu nhiên hiệu quả

## Tóm tắt
Hàm `rand()` trong ngôn ngữ lập trình C là một công cụ quan trọng để sinh số ngẫu nhiên. Nó thuộc thư viện chuẩn `<stdlib.h>` và thường được sử dụng trong các ứng dụng yêu cầu ngẫu nhiên hóa, như game, mô phỏng hoặc trong các thuật toán cần tính ngẫu nhiên.

## Tài liệu
### Mục đích
Hàm `rand()` được thiết kế để tạo ra một số nguyên ngẫu nhiên trong khoảng từ 0 đến `RAND_MAX`, với `RAND_MAX` là một hằng số được định nghĩa trong thư viện `<stdlib.h>`.

### Cú pháp
```c
#include <stdlib.h>

int rand(void);
```

### Sử dụng
Để sử dụng hàm `rand()`, bạn cần:
1. Bao gồm thư viện `<stdlib.h>`.
2. Gọi hàm `rand()` để nhận giá trị ngẫu nhiên.

### Chi tiết
- Hàm `rand()` không nhận tham số.
- Giá trị trả về là một số nguyên dương trong khoảng từ 0 đến `RAND_MAX`, có thể khác nhau tùy vào hệ thống nhưng thường có giá trị tối đa là 32767.
- Để tạo ra một chuỗi số ngẫu nhiên khác nhau mỗi lần chạy chương trình, bạn có thể sử dụng hàm `srand()` để thiết lập giá trị khởi tạo (seed) cho bộ sinh số ngẫu nhiên.

## Ví dụ
### Ví dụ cơ bản
Dưới đây là một ví dụ đơn giản để sử dụng hàm `rand()`:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Khởi tạo seed cho bộ sinh số ngẫu nhiên
    srand(time(NULL));
    
    // Sinh và in ra 5 số ngẫu nhiên
    for (int i = 0; i < 5; i++) {
        printf("%d\n", rand());
    }
    
    return 0;
}
```

### Ví dụ với giới hạn
Nếu bạn muốn sinh số ngẫu nhiên trong khoảng từ 1 đến 100, bạn có thể làm như sau:

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(NULL));
    
    // Sinh số ngẫu nhiên từ 1 đến 100
    int random_number = (rand() % 100) + 1;
    printf("Số ngẫu nhiên: %d\n", random_number);
    
    return 0;
}
```

## Giải thích
- **Giá trị khởi tạo (Seed)**: Hàm `srand()` được sử dụng để thiết lập seed cho hàm `rand()`. Nếu không gọi `srand()`, mỗi lần chạy chương trình sẽ tạo ra cùng một chuỗi số ngẫu nhiên.
- **RAND_MAX**: Khi sử dụng `rand()`, giá trị tối đa mà nó có thể trả về được xác định bởi hằng số `RAND_MAX`. Bạn nên kiểm tra giá trị này nếu cần đảm bảo rằng các số ngẫu nhiên nằm trong một giới hạn cụ thể.
- **Không ngẫu nhiên hoàn toàn**: Hàm `rand()` không phải là bộ sinh số ngẫu nhiên hoàn toàn. Kết quả có thể không đủ tốt cho các ứng dụng yêu cầu tính ngẫu nhiên cao.

## Tóm tắt một câu
Hàm `rand()` trong C cho phép sinh ra các số nguyên ngẫu nhiên trong khoảng từ 0 đến `RAND_MAX`, rất hữu ích trong nhiều ứng dụng lập trình.