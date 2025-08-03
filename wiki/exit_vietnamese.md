<!--
Meta Description: # Lệnh exit trong ngôn ngữ lập trình C: Hướng dẫn chi tiết ## Tóm tắt Lệnh `exit` trong ngôn ngữ lập trình C được sử dụng để kết thúc chương trình một...
Meta Keywords: trình, chương, exit, cho, trạng
-->

# Lệnh exit trong ngôn ngữ lập trình C: Hướng dẫn chi tiết

## Tóm tắt
Lệnh `exit` trong ngôn ngữ lập trình C được sử dụng để kết thúc chương trình một cách an toàn, đồng thời trả về một mã trạng thái cho hệ điều hành. 

## Tài liệu
Lệnh `exit` là một hàm trong thư viện tiêu chuẩn C, được định nghĩa trong tệp tiêu đề `<stdlib.h>`. Hàm này giúp dừng việc thực hiện chương trình và trả về giá trị cho hệ điều hành, cho biết liệu chương trình đã hoàn thành thành công hay có lỗi xảy ra.

### Cú pháp
```c
#include <stdlib.h>

void exit(int status);
```

### Tham số
- `status`: Một số nguyên đại diện cho mã trạng thái khi chương trình kết thúc. Thông thường, giá trị `0` cho biết chương trình đã hoàn thành thành công, trong khi bất kỳ giá trị khác nào cũng chỉ ra sự cố hoặc lỗi.

### Mục đích
- Dừng chương trình: `exit` cho phép bạn kết thúc chương trình tại bất kỳ điểm nào trong mã nguồn.
- Trả về mã trạng thái: Mã trạng thái trả về có thể được sử dụng để truyền đạt thông tin về trạng thái hoàn thành của chương trình cho các chương trình khác hoặc cho hệ điều hành.

## Ví dụ
### Ví dụ cơ bản
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("Chương trình đang chạy...\n");
    exit(0); // Kết thúc chương trình thành công
}
```

### Ví dụ với mã lỗi
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("Đã xảy ra lỗi!\n");
    exit(1); // Kết thúc chương trình với mã lỗi
}
```

## Giải thích
- **Sử dụng không đúng:** Tránh gọi `exit` trong các vòng lặp hoặc các hàm không phải là `main`, nếu bạn không muốn dừng hoàn toàn chương trình.
- **Mất dữ liệu:** Gọi `exit` có thể không thực hiện các thao tác dọn dẹp, như giải phóng bộ nhớ hoặc ghi dữ liệu vào tệp. Đảm bảo rằng bạn đã hoàn tất tất cả các thao tác cần thiết trước khi sử dụng lệnh này.
- **Mã trạng thái:** Thao tác với mã trạng thái của `exit` có thể giúp bạn kiểm soát hành vi của các chương trình con hoặc các script chạy từ dòng lệnh.

## Tóm tắt một dòng
Lệnh `exit` trong C cho phép bạn kết thúc một chương trình và trả về mã trạng thái cho hệ điều hành, đảm bảo quản lý tài nguyên và thông báo về tình trạng của chương trình.