<!--
Meta Description: # Cのstrstr関数：文字列検索のエキスパートガイド ## 概要 `strstr`関数は、C言語の文字列操作において特定の文字列を別の文字列内で検索するための関数です。指定された文字列が最初に現れる位置を指し示すポインタを返します。 ## ドキュメンテーション ### 目的 `strstr`は、...
Meta Keywords: strstr, haystack, needle, char, const
-->

# Cのstrstr関数：文字列検索のエキスパートガイド

## 概要
`strstr`関数は、C言語の文字列操作において特定の文字列を別の文字列内で検索するための関数です。指定された文字列が最初に現れる位置を指し示すポインタを返します。

## ドキュメンテーション
### 目的
`strstr`は、指定したサブストリングが与えられた文字列内に存在するかどうかを調査し、最初に見つかった位置を返すための関数です。

### 使用法
`strstr`の基本的なシンタックスは以下の通りです：

```c
char *strstr(const char *haystack, const char *needle);
```

- **引数**:
  - `haystack`: 検索対象の文字列（大文字小文字を区別）。
  - `needle`: 検索するサブストリング。

- **戻り値**:
  - `needle`が`haystack`内で見つかった場合、その位置を指すポインタ。
  - 見つからなかった場合は`NULL`を返します。

### 詳細
`strstr`はC標準ライブラリの`<string.h>`ヘッダファイルに定義されています。この関数を使用することで、文字列の検索が容易に行えます。返されるポインタは、元の文字列の一部を指し示します。したがって、`haystack`が変更されない場合、`strstr`の結果も有効なポインタとなります。

## 例
以下に`strstr`関数の基本的な使用例を示します。

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Hello, World!";
    const char *needle = "World";
    
    char *result = strstr(haystack, needle);
    
    if (result) {
        printf("見つかりました: %s\n", result);
    } else {
        printf("見つかりませんでした。\n");
    }
    
    return 0;
}
```

この例では、文字列「World」が「Hello, World!」内で見つかり、見つかった位置からの文字列が表示されます。

## 説明
`strstr`を使用する際の一般的な落とし穴や注意点があります。

- **大文字と小文字**: `strstr`は大文字小文字を区別します。例えば、"hello"と"Hello"は異なる文字列と見なされるため、必要に応じて大文字小文字を統一する必要があります。

- **NULLポインタ**: `haystack`または`needle`がNULLの場合、未定義動作が発生します。呼び出す前に、ポインタがNULLでないことを確認してください。

- **空のneedle**: `needle`が空文字列（""）の場合、`haystack`の最初の位置を返します。

## 一文要約
`strstr`関数は、C言語で特定のサブストリングを文字列内で検索し、その位置を見つけるための便利な関数です。