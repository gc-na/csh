<!--
Meta Description: # C言語のbsearch関数：高速な二分探索アルゴリズム ## 概要 `bsearch`関数は、C言語においてソートされた配列から特定の値を迅速に検索するための標準ライブラリ関数です。この関数は二分探索アルゴリズムを使用しており、平均的な計算量はO(log n)です。 ## ドキュメンテーション ...
Meta Keywords: int, bsearch, void, const, key
-->

# C言語のbsearch関数：高速な二分探索アルゴリズム

## 概要
`bsearch`関数は、C言語においてソートされた配列から特定の値を迅速に検索するための標準ライブラリ関数です。この関数は二分探索アルゴリズムを使用しており、平均的な計算量はO(log n)です。

## ドキュメンテーション
### 機能
`bsearch`は、指定された値がソートされた配列内に存在するかどうかを判断し、見つかった場合にはそのポインタを返します。

### 使用法
`bsearch`関数の基本的なシグネチャは以下の通りです：

```c
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
              int (*compar)(const void*, const void*));
```

#### パラメータ
- **key**: 検索したい値のポインタ。
- **base**: ソートされた配列の先頭要素のポインタ。
- **nmemb**: 配列の要素数。
- **size**: 各要素のサイズ（バイト数）。
- **compar**: 2つの要素を比較するための関数ポインタ。戻り値が0のとき、要素は等しいとみなされます。

### 戻り値
- 検索に成功した場合、`key`が見つかった位置へのポインタが返されます。
- 検索に失敗した場合、`NULL`が返されます。

## 例
以下は、`bsearch`関数の基本的な使用例です。

```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
    int key = 5;
    int* result;

    result = (int*)bsearch(&key, arr, 9, sizeof(int), compare);

    if (result != NULL) {
        printf("Found: %d\n", *result);
    } else {
        printf("Not found.\n");
    }

    return 0;
}
```

## 説明
### 一般的な落とし穴
- **配列のソート**: `bsearch`を使用する前に、配列がソートされていることを確認してください。ソートされていない配列に対して使用すると、未定義の動作を引き起こす可能性があります。
- **比較関数の実装**: 比較関数は正確に実装する必要があります。戻り値が正しくない場合、検索結果が不正確になることがあります。

### 補足
- `bsearch`は、配列の要素数が大きい場合に特に効果的です。小さな配列では、線形探索の方が効率的になることがあります。

## 一文要約
`bsearch`は、C言語におけるソートされた配列から特定の値を迅速に検索するための関数です。