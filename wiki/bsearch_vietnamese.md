<!--
Meta Description: # Tìm kiếm nhị phân trong C với hàm bsearch ## Tóm tắt Hàm `bsearch` trong ngôn ngữ lập trình C được sử dụng để tìm kiếm nhị phân trong một mảng đã đư...
Meta Keywords: phần, hàm, tìm, trong, mảng
-->

# Tìm kiếm nhị phân trong C với hàm bsearch

## Tóm tắt
Hàm `bsearch` trong ngôn ngữ lập trình C được sử dụng để tìm kiếm nhị phân trong một mảng đã được sắp xếp, cho phép người dùng tìm kiếm nhanh chóng một phần tử trong mảng.

## Tài liệu

### Mục đích
Hàm `bsearch` giúp người lập trình tìm kiếm một phần tử trong mảng theo phương pháp tìm kiếm nhị phân, điều này yêu cầu mảng phải được sắp xếp trước đó. Nếu phần tử được tìm thấy, hàm sẽ trả về con trỏ đến phần tử đó; nếu không, hàm sẽ trả về NULL.

### Cú pháp
```c
void *bsearch(const void *key, const void *base, size_t nmemb, size_t size,
              int (*compar)(const void *, const void *));
```

### Tham số
- `key`: Con trỏ đến phần tử cần tìm.
- `base`: Con trỏ đến mảng đã sắp xếp.
- `nmemb`: Số lượng phần tử trong mảng.
- `size`: Kích thước của mỗi phần tử trong mảng (tính bằng byte).
- `compar`: Con trỏ đến hàm so sánh, hàm này nhận hai con trỏ đến các phần tử và trả về:
  - Giá trị âm nếu phần tử thứ nhất nhỏ hơn phần tử thứ hai.
  - Giá trị dương nếu phần tử thứ nhất lớn hơn phần tử thứ hai.
  - Giá trị 0 nếu hai phần tử bằng nhau.

### Trả về
- Nếu tìm thấy phần tử, hàm trả về con trỏ đến phần tử đó trong mảng.
- Nếu không tìm thấy, hàm trả về NULL.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng hàm `bsearch`:

```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return (*(int *)a - *(int *)b);
}

int main() {
    int arr[] = {1, 3, 5, 7, 9};
    int key = 5;
    int *result;

    result = (int *)bsearch(&key, arr, 5, sizeof(int), compare);

    if (result != NULL) {
        printf("Phần tử %d được tìm thấy.\n", *result);
    } else {
        printf("Phần tử không được tìm thấy.\n");
    }

    return 0;
}
```

## Giải thích
### Những cạm bẫy và lưu ý
- Mảng phải được sắp xếp trước khi sử dụng hàm `bsearch`. Nếu không, kết quả sẽ không chính xác.
- Hàm so sánh phải được định nghĩa chính xác để đảm bảo hoạt động tìm kiếm diễn ra suôn sẻ.
- `bsearch` là hàm không an toàn với kiểu dữ liệu không phải cơ bản; do đó, người dùng phải đảm bảo rằng kiểu dữ liệu được sử dụng trong hàm so sánh là chính xác.

## Tóm tắt ngắn gọn
Hàm `bsearch` trong C cung cấp phương pháp tìm kiếm nhị phân hiệu quả cho các mảng đã sắp xếp.