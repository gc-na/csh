<!--
Meta Description: # Từ Khóa "signed" trong Ngôn Ngữ Lập Trình C: Hiểu Biết Cơ Bản ## Tóm Tắt Trong ngôn ngữ lập trình C, từ khóa "signed" được sử dụng để chỉ định rằng ...
Meta Keywords: signed, kiểu, int, trong, dụng
-->

# Từ Khóa "signed" trong Ngôn Ngữ Lập Trình C: Hiểu Biết Cơ Bản

## Tóm Tắt
Trong ngôn ngữ lập trình C, từ khóa "signed" được sử dụng để chỉ định rằng một kiểu dữ liệu có thể lưu trữ cả giá trị âm và dương. Đây là một phần quan trọng trong việc xử lý số nguyên và ảnh hưởng đến phạm vi mà kiểu dữ liệu đó có thể đại diện.

## Tài Liệu
### Mục Đích
Từ khóa "signed" được sử dụng để xác định biểu thức kiểu số nguyên có thể mang giá trị âm. Theo mặc định, kiểu số nguyên trong C là "signed". Việc sử dụng "signed" là cần thiết khi bạn muốn làm rõ rằng biến có khả năng lưu trữ giá trị âm.

### Cách Sử Dụng
Cú pháp để sử dụng "signed" trong C như sau:
```c
signed int a; // Khai báo biến a có kiểu signed int
```
Khi không chỉ định "signed" cho kiểu int, nó vẫn mặc định là signed. Bạn cũng có thể sử dụng "signed" với các kiểu dữ liệu khác như char và short.

### Chi Tiết
- **Kích Thước**: Kích thước của một biến signed thường là 4 byte (32 bit) cho int trong hầu hết các hệ thống.
- **Phạm Vi**: Đối với một biến signed int, phạm vi giá trị là từ -2,147,483,648 đến 2,147,483,647.
- **Kết Hợp với các Kiểu Khác**: Bạn có thể kết hợp "signed" với các kiểu khác như "short", "long", và "char".

## Ví Dụ
### Ví Dụ Cơ Bản
```c
#include <stdio.h>

int main() {
    signed int a = -10;
    signed int b = 20;
    signed int sum = a + b;
    
    printf("Tổng: %d\n", sum); // In ra: Tổng: 10
    return 0;
}
```

### Ví Dụ Sử Dụng Với Char
```c
#include <stdio.h>

int main() {
    signed char c = -5; // Khai báo một ký tự signed
    printf("Giá trị của c: %d\n", c); // In ra: Giá trị của c: -5
    return 0;
}
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Không Cần Thiết**: Thường thì bạn không cần chỉ định "signed" cho kiểu int vì nó đã mặc định là signed. Tuy nhiên, việc làm rõ có thể giúp tăng tính dễ đọc của mã.
- **Kích Thước Không Đồng Nhất**: Trong một số hệ thống, kích thước của kiểu signed có thể khác nhau. Hãy chắc chắn kiểm tra kích thước kiểu dữ liệu trên hệ thống của bạn.

### Lưu Ý
- **Sự Khác Biệt Giữa Signed và Unsigned**: Kiểu "unsigned" chỉ cho phép giá trị dương, mang lại phạm vi lớn hơn cho các số dương nhưng không cho phép các số âm.
- **Hiệu Suất**: Việc sử dụng signed hay unsigned không ảnh hưởng nhiều đến hiệu suất, nhưng việc lựa chọn đúng loại kiểu dữ liệu sẽ giúp tránh được lỗi trong tính toán.

## Tóm Tắt Một Câu
Từ khóa "signed" trong ngôn ngữ C xác định rằng một kiểu dữ liệu có thể lưu trữ giá trị âm và dương, giúp lập trình viên kiểm soát phạm vi của các biến số nguyên.