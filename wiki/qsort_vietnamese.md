<!--
Meta Description: # Hàm qsort trong C: Hướng dẫn và Ví dụ Sử Dụng ## Tóm tắt Hàm `qsort` trong ngôn ngữ lập trình C là một hàm tiêu chuẩn được sử dụng để sắp xếp các ph...
Meta Keywords: hàm, qsort, mảng, một, phần
-->

# Hàm qsort trong C: Hướng dẫn và Ví dụ Sử Dụng

## Tóm tắt
Hàm `qsort` trong ngôn ngữ lập trình C là một hàm tiêu chuẩn được sử dụng để sắp xếp các phần tử trong một mảng theo thứ tự tăng dần hoặc giảm dần.

## Tài liệu
Hàm `qsort` thuộc thư viện `<stdlib.h>` và được sử dụng để thực hiện sắp xếp nhanh (quicksort) trên các mảng. Cú pháp của hàm như sau:

```c
void qsort(void *base, size_t num, size_t size, int (*compar)(const void *, const void *));
```

### Tham số:
- `base`: Con trỏ đến mảng cần được sắp xếp.
- `num`: Số lượng phần tử trong mảng.
- `size`: Kích thước (byte) của mỗi phần tử trong mảng.
- `compar`: Con trỏ đến hàm so sánh, hàm này nhận hai con trỏ đến các phần tử cần so sánh và trả về một số nguyên.

### Mục đích:
Mục đích của `qsort` là sắp xếp một mảng các phần tử theo thứ tự đã chỉ định (tăng dần hoặc giảm dần) bằng cách sử dụng phương pháp sắp xếp nhanh.

### Cách sử dụng:
Để sử dụng `qsort`, người dùng cần định nghĩa một hàm so sánh mà sẽ được truyền vào hàm này. Hàm so sánh sẽ xác định thứ tự sắp xếp cho các phần tử.

## Ví dụ
Dưới đây là một ví dụ đơn giản minh họa cách sử dụng hàm `qsort` để sắp xếp một mảng số nguyên.

```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int arr[] = {34, 7, 23, 32, 5, 62};
    size_t arr_size = sizeof(arr) / sizeof(arr[0]);

    qsort(arr, arr_size, sizeof(int), compare);

    printf("Mảng sau khi sắp xếp: ");
    for (size_t i = 0; i < arr_size; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
```

## Giải thích
Khi sử dụng `qsort`, cần lưu ý một số điểm sau:
- Hàm so sánh phải trả về số dương, số âm hoặc 0 tùy thuộc vào việc phần tử đầu vào lớn hơn, nhỏ hơn hoặc bằng nhau.
- Kích thước của mảng và kích thước của mỗi phần tử cần được truyền chính xác.
- `qsort` có thể không hoạt động đúng nếu mảng chứa các phần tử không thể so sánh được.

## Tóm tắt một dòng
Hàm `qsort` trong C cung cấp một phương pháp hiệu quả để sắp xếp các phần tử trong mảng theo thứ tự đã chỉ định thông qua việc sử dụng hàm so sánh.