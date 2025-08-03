<!--
Meta Description: # Sử Dụng Hàm fprintf trong Ngôn Ngữ Lập Trình C ## Tóm tắt Hàm `fprintf` trong ngôn ngữ lập trình C được sử dụng để ghi dữ liệu vào một luồng tệp the...
Meta Keywords: tệp, định, fprintf, ghi, một
-->

# Sử Dụng Hàm fprintf trong Ngôn Ngữ Lập Trình C

## Tóm tắt
Hàm `fprintf` trong ngôn ngữ lập trình C được sử dụng để ghi dữ liệu vào một luồng tệp theo định dạng cụ thể, cho phép người lập trình định dạng đầu ra một cách linh hoạt.

## Tài liệu
Hàm `fprintf` thuộc về thư viện tiêu chuẩn `<stdio.h>`. Mục đích chính của hàm này là ghi dữ liệu vào một tệp hoặc luồng đầu ra với định dạng mà người dùng chỉ định.

### Cú pháp
```c
int fprintf(FILE *stream, const char *format, ...);
```

### Tham số
- `FILE *stream`: Con trỏ đến luồng tệp mà bạn muốn ghi dữ liệu vào.
- `const char *format`: Chuỗi định dạng chứa các ký tự định dạng (như `%d`, `%s`, `%f`, v.v.) để xác định cách thức hiển thị dữ liệu.
- `...`: Một danh sách các đối số bổ sung tương ứng với các ký tự định dạng trong chuỗi `format`.

### Giá trị trả về
Hàm `fprintf` trả về số ký tự đã ghi vào luồng tệp. Nếu xảy ra lỗi, giá trị trả về sẽ là một giá trị âm.

## Ví dụ
### Ví dụ cơ bản
Dưới đây là một ví dụ đơn giản sử dụng `fprintf` để ghi dữ liệu vào một tệp:

```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w");
    if (file == NULL) {
        perror("Không thể mở tệp");
        return -1;
    }
    
    int age = 25;
    const char *name = "Nguyen Van A";
    
    fprintf(file, "Tên: %s, Tuổi: %d\n", name, age);
    
    fclose(file);
    return 0;
}
```
Trong ví dụ này, tên và tuổi của một người được ghi vào tệp `output.txt` với định dạng mong muốn.

## Giải thích
Khi sử dụng `fprintf`, có một số điểm cần lưu ý:

1. **Mở tệp**: Luôn đảm bảo rằng tệp đã được mở thành công trước khi gọi `fprintf`. Nếu `fopen` trả về NULL, điều đó có nghĩa là tệp không thể được mở.
   
2. **Định dạng không chính xác**: Nếu số lượng hoặc loại các đối số không khớp với các ký tự định dạng trong chuỗi `format`, điều này có thể dẫn đến kết quả không mong muốn hoặc lỗi runtime.

3. **Đóng tệp**: Sau khi hoàn tất việc ghi, luôn luôn đóng tệp bằng `fclose` để đảm bảo rằng tất cả dữ liệu đã được ghi và tài nguyên được giải phóng.

4. **Kiểm tra lỗi**: Nên kiểm tra giá trị trả về của `fprintf` để xác nhận rằng việc ghi đã diễn ra thành công.

## Tóm tắt một dòng
Hàm `fprintf` trong C cho phép ghi dữ liệu vào tệp theo định dạng tùy chỉnh, hỗ trợ việc xuất dữ liệu linh hoạt và dễ dàng.