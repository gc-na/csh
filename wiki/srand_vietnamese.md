<!--
Meta Description: # Hàm srand trong C: Cách sử dụng và ứng dụng ## Tóm tắt Hàm `srand` trong C được sử dụng để khởi tạo trình tạo số ngẫu nhiên, giúp đảm bảo rằng các s...
Meta Keywords: nhiên, ngẫu, được, tạo, trình
-->

# Hàm srand trong C: Cách sử dụng và ứng dụng

## Tóm tắt
Hàm `srand` trong C được sử dụng để khởi tạo trình tạo số ngẫu nhiên, giúp đảm bảo rằng các số ngẫu nhiên được tạo ra bởi hàm `rand` là khác nhau mỗi khi chương trình được chạy.

## Tài liệu
Hàm `srand` là một phần của thư viện chuẩn C `<stdlib.h>`. Mục đích chính của hàm này là thiết lập giá trị khởi tạo cho trình tạo số ngẫu nhiên. Nếu không sử dụng `srand`, mỗi lần chạy chương trình, hàm `rand` sẽ trả về cùng một dãy số ngẫu nhiên.

### Cú pháp
```c
#include <stdlib.h>

void srand(unsigned int seed);
```

### Tham số
- `seed`: Một giá trị kiểu `unsigned int` được sử dụng để khởi tạo trình tạo số ngẫu nhiên. Giá trị này thường được lấy từ thời gian hiện tại để đảm bảo tính ngẫu nhiên.

### Mô tả
Hàm `srand` nên được gọi một lần trước khi sử dụng `rand`. Việc khởi tạo này rất quan trọng vì nếu không, mỗi lần chương trình được chạy, `rand` sẽ trả về cùng một dãy số ngẫu nhiên, điều này làm giảm tính ngẫu nhiên trong các ứng dụng yêu cầu sự ngẫu nhiên cao như trò chơi, mô phỏng, hoặc thử nghiệm.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng `srand` và `rand`:

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    // Khởi tạo số ngẫu nhiên
    srand(time(NULL)); // Sử dụng thời gian hiện tại làm seed

    // Tạo và in ra 5 số ngẫu nhiên
    for (int i = 0; i < 5; i++) {
        int randomNum = rand();
        printf("%d\n", randomNum);
    }

    return 0;
}
```

## Giải thích
- **Lỗi thường gặp**: Một lỗi phổ biến là không gọi `srand` trước `rand`, dẫn đến việc nhận được cùng một dãy số ngẫu nhiên mỗi khi chương trình được chạy.
- **Tính ngẫu nhiên**: Sử dụng `time(NULL)` để làm seed giúp đảm bảo rằng mỗi lần chạy chương trình sẽ nhận được một dãy số khác nhau, tuy nhiên, nếu hai chương trình được chạy trong cùng một giây, chúng vẫn có thể nhận được các số giống nhau. Để tránh điều này, có thể kết hợp thêm các yếu tố khác như ID tiến trình hoặc một số giá trị khác.
- **Lưu ý**: `srand` chỉ cần được gọi một lần trong toàn bộ chương trình. Gọi lại nhiều lần có thể không cần thiết và có thể ảnh hưởng đến tính ngẫu nhiên của các số ngẫu nhiên tiếp theo.

## Tóm tắt một dòng
Hàm `srand` trong C được sử dụng để khởi tạo trình tạo số ngẫu nhiên, đảm bảo rằng các số ngẫu nhiên được tạo ra bởi hàm `rand` là khác nhau mỗi lần chạy chương trình.