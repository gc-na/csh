<!--
Meta Description: # C言語の関数「strrchr」: 文字列内の最後の特定文字を検索する ## 概要 `strrchr`は、C言語の標準ライブラリに含まれる文字列操作関数で、指定した文字が文字列内で最後に出現する位置を検索します。この関数は、文字列の探索や解析において非常に便利です。 ## ドキュメンテーション #...
Meta Keywords: strrchr, result, char, str, include
-->

# C言語の関数「strrchr」: 文字列内の最後の特定文字を検索する

## 概要
`strrchr`は、C言語の標準ライブラリに含まれる文字列操作関数で、指定した文字が文字列内で最後に出現する位置を検索します。この関数は、文字列の探索や解析において非常に便利です。

## ドキュメンテーション
### 目的
`strrchr`関数は、指定した文字が文字列内で最も右側に位置する場所を見つけ、そのポインタを返すことを目的としています。見つからなかった場合はNULLを返します。

### 使用法
```c
#include <string.h>

char *strrchr(const char *s, int c);
```
- **引数**:
  - `s`: 探索対象の文字列。
  - `c`: 検索する文字（ASCII値で指定）。

- **戻り値**:
  - `s`内で検索された文字`c`の最後の出現位置へのポインタ。
  - `c`が`'\0'`（ヌル文字）の場合、文字列の終わりを示すポインタを返します。
  - 文字が見つからない場合はNULLを返します。

### 詳細
`strrchr`は、文字列を後ろから前に向かって探索し、最初に見つけた指定した文字の位置を返します。このため、他の文字列検索関数（例えば`strchr`）とは異なり、右側からの検索が行われます。

## 例
以下は`strrchr`の基本的な使用例です。

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, World!";
    char *result;

    // 'o'の最後の出現を検索
    result = strrchr(str, 'o');
    if (result != NULL) {
        printf("Found 'o' at position: %ld\n", result - str);
    } else {
        printf("'o' was not found.\n");
    }

    // ヌル文字の検索
    result = strrchr(str, '\0');
    if (result != NULL) {
        printf("Null character found at position: %ld\n", result - str);
    }

    return 0;
}
```

## 説明
- `strrchr`を使用する際の一般的な落とし穴は、戻り値がNULLである場合のチェックを忘れることです。NULLチェックを行わないと、無効なメモリアクセスが発生し、プログラムがクラッシュする可能性があります。
- また、`c`に指定する文字は、常に`int`型で渡す必要がありますが、通常は`char`型の文字を直接指定することが一般的です。

## 一文要約
`strrchr`は、C言語で文字列内の指定した文字の最後の出現位置を検索するための便利な関数です。