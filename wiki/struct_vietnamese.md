<!--
Meta Description: # C Struct: Cấu Trúc Dữ Liệu Trong Ngôn Ngữ Lập Trình C ## Tóm tắt Cấu trúc (struct) trong ngôn ngữ lập trình C là một kiểu dữ liệu người dùng cho phé...
Meta Keywords: cấu, trúc, struct, liệu, các
-->

# C Struct: Cấu Trúc Dữ Liệu Trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Cấu trúc (struct) trong ngôn ngữ lập trình C là một kiểu dữ liệu người dùng cho phép nhóm nhiều biến khác nhau lại với nhau thành một đơn vị duy nhất. Điều này giúp tổ chức dữ liệu một cách hiệu quả hơn.

## Tài liệu
Cấu trúc trong C được định nghĩa bằng từ khóa `struct`, và nó cho phép bạn tạo ra các kiểu dữ liệu phức tạp hơn bằng cách kết hợp nhiều kiểu dữ liệu cơ bản. Cấu trúc có thể chứa nhiều biến với các kiểu dữ liệu khác nhau, và bạn có thể truy cập các thành viên của nó thông qua toán tử `.`.

### Cú pháp định nghĩa cấu trúc:
```c
struct TênCấuTrúc {
    KiểuDữLiệu tênBiến1;
    KiểuDữLiệu tênBiến2;
    // ...
};
```

### Khai báo biến kiểu cấu trúc:
```c
struct TênCấuTrúc biến;
```

### Truy cập các thành viên của cấu trúc:
```c
biến.tênBiến1 = giáTrị;
```

Cấu trúc không chỉ giúp tổ chức dữ liệu mà còn cho phép người lập trình dễ dàng quản lý và truyền tải thông tin giữa các hàm.

## Ví dụ
### Định nghĩa và sử dụng cấu trúc cơ bản:
```c
#include <stdio.h>

// Định nghĩa cấu trúc
struct Diem {
    int x;
    int y;
};

int main() {
    // Khai báo biến kiểu cấu trúc
    struct Diem diem1;
    
    // Gán giá trị cho các thành viên
    diem1.x = 10;
    diem1.y = 20;
    
    // In ra giá trị
    printf("Diem co toa do: (%d, %d)\n", diem1.x, diem1.y);
    return 0;
}
```

### Cấu trúc lồng nhau:
```c
#include <stdio.h>

// Định nghĩa cấu trúc lồng nhau
struct DiaChi {
    char duong[100];
    char thanhPho[50];
};

struct Nguoi {
    char ten[50];
    struct DiaChi diaChi;
};

int main() {
    struct Nguoi nguoi1;
    
    // Gán giá trị
    strcpy(nguoi1.ten, "Nguyen Van A");
    strcpy(nguoi1.diaChi.duong, "123 Duong ABC");
    strcpy(nguoi1.diaChi.thanhPho, "Hanoi");
    
    // In ra thông tin
    printf("Ten: %s\n", nguoi1.ten);
    printf("Dia chi: %s, %s\n", nguoi1.diaChi.duong, nguoi1.diaChi.thanhPho);
    return 0;
}
```

## Giải thích
- **Lưu ý về kích thước**: Kích thước của cấu trúc sẽ phụ thuộc vào các kiểu dữ liệu mà nó chứa, cũng như cách mà bộ nhớ được quản lý bởi trình biên dịch.
- **Truy cập thành viên**: Đảm bảo rằng bạn sử dụng toán tử `.` hoặc `->` (đối với con trỏ) đúng cách khi truy cập các thành viên của cấu trúc.
- **Tính khả chuyển**: Cấu trúc có thể được truyền như một tham số đến các hàm, nhưng nên lưu ý rằng việc truyền cấu trúc lớn có thể gây tốn kém về hiệu suất. Thay vào đó, bạn có thể truyền con trỏ đến cấu trúc.

## Tóm tắt một dòng
Cấu trúc trong C là một công cụ mạnh mẽ cho phép nhóm nhiều biến của các kiểu dữ liệu khác nhau thành một thực thể duy nhất, giúp tổ chức và quản lý dữ liệu hiệu quả hơn.