<!--
Meta Description: # Cách Sử Dụng Câu Lệnh "else" Trong Ngôn Ngữ Lập Trình C ## Tóm Tắt Câu lệnh "else" trong ngôn ngữ lập trình C được sử dụng để thực hiện một khối mã ...
Meta Keywords: câu, lệnh, else, điều, kiện
-->

# Cách Sử Dụng Câu Lệnh "else" Trong Ngôn Ngữ Lập Trình C

## Tóm Tắt
Câu lệnh "else" trong ngôn ngữ lập trình C được sử dụng để thực hiện một khối mã khác nếu điều kiện trong câu lệnh "if" không được thỏa mãn. Đây là một phần quan trọng trong cấu trúc điều kiện, giúp lập trình viên kiểm soát luồng thực thi của chương trình.

## Tài Liệu
Câu lệnh "else" thường đi kèm với câu lệnh "if". Khi điều kiện trong câu lệnh "if" trả về giá trị sai (false), khối mã trong câu lệnh "else" sẽ được thực thi. Cú pháp cơ bản của câu lệnh "else" là:

```c
if (điều kiện) {
    // Khối mã sẽ được thực thi nếu điều kiện đúng
} else {
    // Khối mã sẽ được thực thi nếu điều kiện sai
}
```

### Mục Đích
Câu lệnh "else" giúp lập trình viên định nghĩa hành động thay thế khi một điều kiện không được thỏa mãn, từ đó tạo ra các chương trình linh hoạt hơn.

### Cách Sử Dụng
1. **Câu lệnh đơn giản**:
   ```c
   if (x > 0) {
       printf("x là số dương\n");
   } else {
       printf("x không phải là số dương\n");
   }
   ```

2. **Câu lệnh lồng nhau**:
   ```c
   if (a > b) {
       printf("a lớn hơn b\n");
   } else if (a < b) {
       printf("a nhỏ hơn b\n");
   } else {
       printf("a bằng b\n");
   }
   ```

## Ví Dụ
### Ví dụ 1: Sử dụng câu lệnh "else" đơn giản
```c
#include <stdio.h>

int main() {
    int num = -5;
    
    if (num >= 0) {
        printf("Số không âm\n");
    } else {
        printf("Số âm\n");
    }
    return 0;
}
```
**Kết quả**: "Số âm"

### Ví dụ 2: Câu lệnh lồng nhau
```c
#include <stdio.h>

int main() {
    int a = 10, b = 20;
    
    if (a > b) {
        printf("a lớn hơn b\n");
    } else if (a < b) {
        printf("a nhỏ hơn b\n");
    } else {
        printf("a bằng b\n");
    }
    return 0;
}
```
**Kết quả**: "a nhỏ hơn b"

## Giải Thích
### Những Lưu Ý Thường Gặp
- **Thiếu dấu ngoặc nhọn**: Nếu chỉ có một câu lệnh trong khối "if" hoặc "else", bạn có thể bỏ qua dấu ngoặc nhọn. Tuy nhiên, điều này có thể gây nhầm lẫn khi bạn thêm câu lệnh sau này.
- **Sự ưu tiên của điều kiện**: Khi sử dụng cấu trúc lồng nhau, hãy chú ý đến thứ tự kiểm tra các điều kiện để tránh hành vi không mong muốn.

### Ghi Chú Bổ Sung
Câu lệnh "else" có thể được sử dụng kết hợp với nhiều câu lệnh "if" để tạo ra các cấu trúc điều kiện phức tạp hơn. Tuy nhiên, lập trình viên cần đảm bảo rằng các điều kiện được sắp xếp hợp lý để tránh nhầm lẫn trong logic.

## Tóm Tắt Một Câu
Câu lệnh "else" trong ngôn ngữ C cho phép thực hiện một khối mã thay thế khi điều kiện trong câu lệnh "if" không được thỏa mãn.