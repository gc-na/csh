<!--
Meta Description: # C言語における「labs」関数：長整数の絶対値を計算する ## 概要 C言語の「labs」関数は、長整数（long int）の絶対値を計算するための標準ライブラリ関数です。この関数は、負の値を正の値に変換し、プログラムの数値処理を簡素化します。 ## ドキュメンテーション ### 機能 「lab...
Meta Keywords: labs, long, int, 関数は, absolute
-->

# C言語における「labs」関数：長整数の絶対値を計算する

## 概要
C言語の「labs」関数は、長整数（long int）の絶対値を計算するための標準ライブラリ関数です。この関数は、負の値を正の値に変換し、プログラムの数値処理を簡素化します。

## ドキュメンテーション
### 機能
「labs」関数は、引数として受け取った長整数の絶対値を返します。この関数は、数値が負であっても常に正の値を返すため、数値計算や条件文での使用において便利です。

### 使用法
```c
#include <stdlib.h>

long int labs(long int x);
```

- **引数**: `long int x` - 絶対値を計算したい長整数。
- **戻り値**: 引数の絶対値を表す `long int` 型の値。

### 詳細
「labs」関数は、C標準ライブラリの `<stdlib.h>` ヘッダーファイルに定義されています。負の数を入力として与えた場合、関数はその数の正の値を返します。例えば、`labs(-5)` を呼び出すと `5` が返されます。

## 例
以下は「labs」関数の基本的な使用例です。

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    long int num1 = -10;
    long int num2 = 20;
    
    printf("Absolute value of %ld is %ld\n", num1, labs(num1));
    printf("Absolute value of %ld is %ld\n", num2, labs(num2));

    return 0;
}
```

### 出力
```
Absolute value of -10 is 10
Absolute value of 20 is 20
```

## 説明
「labs」関数を使用する際の注意点として、以下の点があります：

- **データ型の制約**: 引数として渡す値が `long int` 型である必要があります。他の整数型（例えば `int` や `long long`）を使用すると、型変換が必要になります。
- **オーバーフロー**: `LONG_MIN` の絶対値は `LONG_MAX` よりも大きいため、 `labs(LONG_MIN)` の結果は未定義です。このため、入力値が `LONG_MIN` の場合は注意が必要です。

## 一文の要約
「labs」関数は、C言語において長整数の絶対値を計算するための便利な関数です。