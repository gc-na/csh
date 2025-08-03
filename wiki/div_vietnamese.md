<!--
Meta Description: # Hàm `div` trong ngôn ngữ lập trình C: Cách sử dụng và ví dụ ## Tóm tắt Hàm `div` trong ngôn ngữ lập trình C được sử dụng để thực hiện phép chia hai ...
Meta Keywords: div, hàm, chia, phép, int
-->

# Hàm `div` trong ngôn ngữ lập trình C: Cách sử dụng và ví dụ

## Tóm tắt
Hàm `div` trong ngôn ngữ lập trình C được sử dụng để thực hiện phép chia hai số nguyên và trả về kết quả dưới dạng một cấu trúc, bao gồm thương và số dư.

## Tài liệu
Hàm `div` là một phần của thư viện `<stdlib.h>` trong C, cho phép lập trình viên thực hiện phép chia giữa hai số nguyên với tính năng trả về cả thương và số dư. Hàm này có cú pháp như sau:

```c
div_t div(int numer, int denom);
```

### Tham số:
- `numer`: Số nguyên tử số (số chia).
- `denom`: Số nguyên mẫu số (số bị chia).

### Giá trị trả về:
Hàm `div` trả về một cấu trúc `div_t`, có hai thành phần:
- `quot`: Thương của phép chia.
- `rem`: Số dư của phép chia.

### Lưu ý:
- Nếu `denom` bằng 0, hành vi của hàm `div` không được xác định và có thể dẫn đến lỗi.

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng hàm `div`:

### Ví dụ 1: Phép chia đơn giản
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int numerator = 10;
    int denominator = 3;
    
    div_t result = div(numerator, denominator);
    
    printf("Thương: %d\n", result.quot);
    printf("Số dư: %d\n", result.rem);
    
    return 0;
}
```

### Ví dụ 2: Phép chia với số âm
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int numerator = -10;
    int denominator = 3;
    
    div_t result = div(numerator, denominator);
    
    printf("Thương: %d\n", result.quot);
    printf("Số dư: %d\n", result.rem);
    
    return 0;
}
```

## Giải thích
Một số lưu ý cần ghi nhớ khi sử dụng hàm `div`:
- Nếu bạn chia cho 0, chương trình sẽ gặp lỗi. Hãy luôn kiểm tra giá trị của `denom` trước khi gọi hàm `div`.
- Hành vi của phép chia với số âm có thể khác so với mong đợi; ví dụ, thương có thể là số âm nếu tử số là số âm và mẫu số là số dương.
- Hàm `div` chỉ hoạt động với kiểu dữ liệu số nguyên.

## Tóm tắt ngắn gọn
Hàm `div` trong C cho phép thực hiện phép chia hai số nguyên và trả về thương cùng số dư trong một cấu trúc `div_t`.