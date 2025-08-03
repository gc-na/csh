<!--
Meta Description: # qsort: The Standard C Library Function for Sorting Arrays ## Synopsis `qsort` is a standard library function in C that provides an efficient way to ...
Meta Keywords: function, qsort, array, void, int
-->

# qsort: The Standard C Library Function for Sorting Arrays

## Synopsis
`qsort` is a standard library function in C that provides an efficient way to sort arrays of any data type using the quicksort algorithm.

## Documentation
### Purpose
The `qsort` function is designed to sort an array in place. It can sort arrays of any data type, as long as a comparison function is provided. The sorting is done using the quicksort algorithm, which is known for its efficiency, particularly with larger datasets.

### Usage
The function prototype for `qsort` is as follows:

```c
void qsort(void *base, size_t num, size_t size, int (*compar)(const void *, const void *));
```

#### Parameters
- **`base`**: A pointer to the first element of the array to be sorted.
- **`num`**: The number of elements in the array.
- **`size`**: The size of each element in the array (in bytes).
- **`compar`**: A pointer to a comparison function that defines the order of the elements. This function should return:
  - A negative value if the first argument is less than the second,
  - Zero if they are equal,
  - A positive value if the first argument is greater than the second.

### Example
Here’s a simple example demonstrating the use of `qsort` to sort an array of integers:

```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return (*(int *)a - *(int *)b);
}

int main() {
    int arr[] = {42, 5, 78, 1, 23};
    size_t arr_size = sizeof(arr) / sizeof(arr[0]);

    qsort(arr, arr_size, sizeof(int), compare);

    printf("Sorted array: ");
    for (size_t i = 0; i < arr_size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```

### Explanation
While `qsort` is a powerful and flexible sorting tool, there are a few common pitfalls to be aware of:

- **Comparison Function**: The comparison function must be correctly implemented. It should handle all possible comparisons between elements of the array and must not assume any specific ordering of values.
  
- **Data Types**: Since `qsort` works with void pointers, it is crucial to cast the pointers to the correct data type inside the comparison function. Failing to do so can lead to undefined behavior.

- **Memory Management**: `qsort` sorts the array in place, meaning it does not allocate additional memory for sorting. Ensure that the array is large enough to accommodate the data.

- **Stability**: The `qsort` function is not a stable sort, which means that elements with equal keys may not retain their original order after sorting.

## One Line Summary
`qsort` is a versatile C library function that efficiently sorts arrays of any data type using a user-defined comparison function.