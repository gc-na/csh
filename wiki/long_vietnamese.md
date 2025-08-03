<!--
Meta Description: # Kiểu Dữ Liệu "long" trong Ngôn Ngữ Lập Trình C ## Tóm tắt Kiểu dữ liệu `long` trong ngôn ngữ lập trình C được sử dụng để lưu trữ các số nguyên lớn h...
Meta Keywords: long, các, dụng, kiểu, trong
-->

# Kiểu Dữ Liệu "long" trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Kiểu dữ liệu `long` trong ngôn ngữ lập trình C được sử dụng để lưu trữ các số nguyên lớn hơn so với kiểu `int`. Nó cho phép lập trình viên xử lý dữ liệu số có giá trị lớn hơn, thường là từ -2^31 đến 2^31-1 trên hệ thống 32-bit.

## Tài liệu
### Mục đích
Kiểu dữ liệu `long` được định nghĩa trong C để cung cấp không gian lưu trữ lớn hơn cho các số nguyên. Điều này hữu ích trong các ứng dụng yêu cầu xử lý số lớn, chẳng hạn như tính toán khoa học hoặc xử lý dữ liệu lớn.

### Cách sử dụng
Để khai báo một biến kiểu `long`, bạn có thể sử dụng cú pháp sau:

```c
long ten_bien;
```

Bạn cũng có thể khởi tạo giá trị ngay lập tức:

```c
long so = 123456789L;
```

Lưu ý rằng ký tự `L` ở cuối giá trị số để chỉ định rằng đây là một số `long`.

### Chi tiết
- Kích thước: Kích thước của `long` phụ thuộc vào hệ thống. Trên hầu hết các hệ thống 32-bit, `long` chiếm 4 byte (32 bit), trong khi trên hệ thống 64-bit, nó có thể chiếm 8 byte (64 bit).
- Phạm vi: Phạm vi của `long` thường là từ -2,147,483,648 đến 2,147,483,647 trên hệ thống 32-bit và từ -9,223,372,036,854,775,808 đến 9,223,372,036,854,775,807 trên hệ thống 64-bit.
- Biến: Bạn có thể sử dụng `long` trong các phép toán số, bao gồm cộng, trừ, nhân, chia như với các kiểu số nguyên khác.

## Ví dụ
### Ví dụ 1: Khai báo và khởi tạo
```c
#include <stdio.h>

int main() {
    long so1 = 1000000000L;
    long so2 = 5000000000L;
    long tong = so1 + so2;
    printf("Tổng: %ld\n", tong);
    return 0;
}
```

### Ví dụ 2: Sử dụng trong hàm
```c
#include <stdio.h>

long tinh_tich(long a, long b) {
    return a * b;
}

int main() {
    long a = 1000000L;
    long b = 2000000L;
    long tich = tinh_tich(a, b);
    printf("Tích: %ld\n", tich);
    return 0;
}
```

## Giải thích
- **Lỗi phổ biến**: Một số lập trình viên có thể gặp phải lỗi khi không sử dụng ký tự `L` cho các giá trị số lớn, dẫn đến việc giá trị bị xem như kiểu `int` và gây ra tràn số.
- **Kích thước không đồng nhất**: Do kích thước của `long` có thể thay đổi giữa các hệ thống, điều này có thể dẫn đến không tương thích nếu mã được chạy trên các nền tảng khác nhau. Bạn nên kiểm tra kích thước của `long` trên hệ thống của bạn bằng cách sử dụng `sizeof(long)`.

## Tóm tắt một dòng
Kiểu dữ liệu `long` trong C cho phép lưu trữ các số nguyên lớn, hữu ích cho các ứng dụng yêu cầu xử lý số có giá trị lớn.