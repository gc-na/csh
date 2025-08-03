<!--
Meta Description: # bsearch: A Comprehensive Guide to Binary Search in C ## Synopsis The `bsearch` function in C is a standard library function that performs a binary s...
Meta Keywords: bsearch, array, const, element, int
-->

# bsearch: A Comprehensive Guide to Binary Search in C

## Synopsis
The `bsearch` function in C is a standard library function that performs a binary search on a sorted array to locate a specified element efficiently.

## Documentation
### Purpose
`bsearch` is used to search for a specified value in a sorted array using the binary search algorithm, which operates in O(log n) time complexity, making it significantly faster than a linear search for large datasets.

### Usage
The function is defined in the `<stdlib.h>` header file and has the following prototype:

```c
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, int (*compar)(const void*, const void*));
```

#### Parameters
- **key**: A pointer to the element to be searched for in the array.
- **base**: A pointer to the first element of the array (sorted).
- **nmemb**: The number of elements in the array.
- **size**: The size of each element in the array.
- **compar**: A comparison function used to compare the `key` with each element in the array. It should return:
  - A negative integer if the first argument is less than the second.
  - Zero if they are equal.
  - A positive integer if the first argument is greater than the second.

### Return Value
`bsearch` returns a pointer to the matching element in the array if found; otherwise, it returns `NULL`.

## Examples
Here are some simple examples illustrating the usage of `bsearch`:

### Example 1: Searching for an Integer
```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int arr[] = {1, 3, 5, 7, 9};
    int key = 5;
    int* result = bsearch(&key, arr, 5, sizeof(int), compare);
    
    if (result != NULL) {
        printf("Element found: %d\n", *result);
    } else {
        printf("Element not found.\n");
    }
    return 0;
}
```

### Example 2: Searching for a String
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int compare(const void* a, const void* b) {
    return strcmp(*(const char**)a, *(const char**)b);
}

int main() {
    const char* arr[] = {"apple", "banana", "cherry", "date", "fig"};
    const char* key = "cherry";
    const char** result = bsearch(&key, arr, 5, sizeof(char*), compare);
    
    if (result != NULL) {
        printf("Element found: %s\n", *result);
    } else {
        printf("Element not found.\n");
    }
    return 0;
}
```

## Explanation
### Common Pitfalls
- **Array Must Be Sorted**: `bsearch` assumes that the input array is sorted. If the array is not sorted, the result is undefined.
- **Comparison Function**: The comparison function must be correctly implemented; otherwise, `bsearch` may return incorrect results.
- **Pointer Handling**: Ensure that the pointers passed to `bsearch` (for the `key` and `comparison function`) are correctly cast to the expected types to avoid segmentation faults or undefined behavior.

### Additional Notes
- The `bsearch` function can only find one instance of a value if it exists in the array. If there are duplicate values, it may not find the first or last occurrence.
- It is important to check the return value of `bsearch` for `NULL` to confirm that the search was successful.

## One Line Summary
The `bsearch` function in C efficiently finds an element in a sorted array using the binary search algorithm.