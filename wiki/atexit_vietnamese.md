<!--
Meta Description: # Hàm atexit trong C: Đăng ký Hàm Huỷ ## Tóm tắt Hàm `atexit` trong ngôn ngữ lập trình C cho phép người lập trình đăng ký một hoặc nhiều hàm để thực t...
Meta Keywords: hàm, đăng, trình, atexit, chương
-->

# Hàm atexit trong C: Đăng ký Hàm Huỷ

## Tóm tắt
Hàm `atexit` trong ngôn ngữ lập trình C cho phép người lập trình đăng ký một hoặc nhiều hàm để thực thi tự động khi chương trình kết thúc, giúp quản lý tài nguyên và thực hiện các thao tác dọn dẹp.

## Tài liệu
Hàm `atexit` được định nghĩa trong thư viện tiêu chuẩn `<stdlib.h>`. Mục đích chính của hàm này là cho phép bạn đăng ký các hàm sẽ được gọi khi chương trình kết thúc. Điều này rất hữu ích cho việc giải phóng bộ nhớ, đóng tệp, hoặc thực hiện các thao tác dọn dẹp khác.

**Cú pháp:**
```c
int atexit(void (*func)(void));
```

**Tham số:**
- `func`: Con trỏ tới hàm không tham số và không trả về giá trị mà bạn muốn đăng ký.

**Trả về:**
- Hàm trả về `0` nếu việc đăng ký thành công.
- Trả về một giá trị khác nếu có lỗi xảy ra.

### Chi tiết
Khi một chương trình C kết thúc, hệ thống sẽ tự động gọi các hàm đã được đăng ký thông qua `atexit` theo thứ tự ngược lại (LIFO - Last In, First Out). Điều này có nghĩa là hàm được đăng ký sau cùng sẽ được gọi trước tiên khi chương trình thoát.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng `atexit`:

```c
#include <stdio.h>
#include <stdlib.h>

void cleanup1() {
    printf("Thực hiện dọn dẹp 1...\n");
}

void cleanup2() {
    printf("Thực hiện dọn dẹp 2...\n");
}

int main() {
    // Đăng ký các hàm dọn dẹp
    atexit(cleanup1);
    atexit(cleanup2);
    
    printf("Chương trình đang chạy...\n");
    
    return 0; // Khi chương trình kết thúc, cleanup2() sẽ được gọi trước, tiếp theo là cleanup1()
}
```

**Kết quả đầu ra:**
```
Chương trình đang chạy...
Thực hiện dọn dẹp 2...
Thực hiện dọn dẹp 1...
```

## Giải thích
- **Lưu ý về số lượng đăng ký**: Bạn có thể gọi `atexit` nhiều lần để đăng ký nhiều hàm. Tuy nhiên, số lượng hàm mà bạn có thể đăng ký phụ thuộc vào hệ thống và thư viện C mà bạn đang sử dụng.
- **Hàm phải phù hợp**: Các hàm bạn đăng ký thông qua `atexit` phải có kiểu trở về `void` và không nhận tham số. Nếu không, hành vi của chương trình sẽ không xác định.
- **Gọi hàm khi thoát**: Nếu chương trình kết thúc do lỗi hoặc bằng cách sử dụng `exit`, các hàm đã đăng ký vẫn sẽ được gọi.

## Tóm tắt một dòng
Hàm `atexit` trong C cho phép bạn đăng ký các hàm để thực hiện tự động khi chương trình kết thúc, giúp quản lý tài nguyên hiệu quả.