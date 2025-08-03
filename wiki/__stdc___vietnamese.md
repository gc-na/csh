<!--
Meta Description: # Tìm hiểu về định danh __STDC__ trong ngôn ngữ lập trình C ## Tóm tắt __STDC__ là một định danh được sử dụng trong ngôn ngữ lập trình C để xác định l...
Meta Keywords: trình, __stdc__, dụng, tiêu, chuẩn
-->

# Tìm hiểu về định danh __STDC__ trong ngôn ngữ lập trình C

## Tóm tắt
__STDC__ là một định danh được sử dụng trong ngôn ngữ lập trình C để xác định liệu trình biên dịch có tuân theo tiêu chuẩn ISO C hay không. Điều này giúp lập trình viên kiểm soát các tính năng của ngôn ngữ và đảm bảo tính tương thích của mã nguồn.

## Tài liệu
Định danh __STDC__ được định nghĩa bởi tiêu chuẩn ISO C và thường được sử dụng trong các chương trình C để kiểm tra xem trình biên dịch có tuân theo tiêu chuẩn C hay không. Khi trình biên dịch hỗ trợ tiêu chuẩn C, nó sẽ định nghĩa __STDC__ là một macro có giá trị bằng 1.

### Mục đích
Mục đích của việc sử dụng __STDC__ là để:
- Kiểm tra tính tương thích của mã nguồn với các tiêu chuẩn C.
- Thực hiện các lệnh biên dịch chỉ khi tiêu chuẩn C được hỗ trợ.

### Cách sử dụng
Để sử dụng __STDC__, lập trình viên thường sử dụng chỉ thị tiền xử lý `#ifdef`, `#ifndef`, `#if`, và `#endif` để kiểm tra sự hiện diện của macro này trong mã nguồn. 

```c
#include <stdio.h>

#ifdef __STDC__
    #define PRINT_VERSION printf("C Standard is supported.\n");
#else
    #define PRINT_VERSION printf("C Standard is NOT supported.\n");
#endif

int main() {
    PRINT_VERSION
    return 0;
}
```

## Ví dụ
Dưới đây là một ví dụ đơn giản về việc sử dụng __STDC__ trong mã nguồn C:

```c
#include <stdio.h>

int main() {
    #ifdef __STDC__
        printf("Chương trình đang sử dụng tiêu chuẩn C.\n");
    #else
        printf("Chương trình không sử dụng tiêu chuẩn C.\n");
    #endif
    return 0;
}
```

Khi biên dịch với một trình biên dịch hỗ trợ tiêu chuẩn C, kết quả sẽ là: `Chương trình đang sử dụng tiêu chuẩn C.`

## Giải thích
Một số điểm cần lưu ý khi sử dụng __STDC__:
- Không phải tất cả các trình biên dịch đều định nghĩa __STDC__. Một số trình biên dịch cũ hoặc không tuân theo tiêu chuẩn có thể không định nghĩa macro này.
- Việc sử dụng __STDC__ giúp lập trình viên viết mã tương thích hơn và có thể tránh được những lỗi không mong muốn khi chạy trên các trình biên dịch khác nhau.
- Nếu kết hợp với các macro khác như __STDC_HOSTED__, lập trình viên có thể kiểm tra các tính năng khác nhau của môi trường biên dịch.

## Tóm tắt một dòng
Định danh __STDC__ là một macro trong ngôn ngữ C dùng để kiểm tra tính tương thích của mã nguồn với tiêu chuẩn ISO C.