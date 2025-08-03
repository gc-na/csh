<!--
Meta Description: # C言語における「case」構文の詳細ガイド ## 概要 C言語の「case」構文は、switch文の一部として使用され、複数の条件分岐を簡潔に表現するための機能です。この構文を利用することで、複数の定数に基づいて異なる処理を実行することが可能です。 ## ドキュメント ### 目的 「case」...
Meta Keywords: case, break, printf, switch, day
-->

# C言語における「case」構文の詳細ガイド

## 概要
C言語の「case」構文は、switch文の一部として使用され、複数の条件分岐を簡潔に表現するための機能です。この構文を利用することで、複数の定数に基づいて異なる処理を実行することが可能です。

## ドキュメント
### 目的
「case」構文は、switch文内で特定の値に基づいて実行するコードブロックを選択するために使用されます。これにより、if-else文を使用するよりも可読性が高く、管理しやすいコードを書くことができます。

### 使用法
`switch`文は、特定の変数を評価し、その値に基づいて対応する`case`ブロックを実行します。基本的な構文は次の通りです。

```c
switch (expression) {
    case constant1:
        // constant1に一致した場合の処理
        break;
    case constant2:
        // constant2に一致した場合の処理
        break;
    default:
        // どのcaseにも一致しなかった場合の処理
}
```

### 詳細
- **expression**: 評価される式で、整数型または列挙型である必要があります。
- **case**: 各caseは、特定の値を指定し、対応する処理を実行します。
- **break**: 各caseブロックの最後に`break`文を置くことで、switch文から抜け出します。これを省略すると、次のcaseにフォールスルー（fall-through）します。
- **default**: すべてのcaseが一致しない場合に実行される部分です。省略することも可能です。

## 例
以下は、`switch-case`構文の基本的な使用例です。

```c
#include <stdio.h>

int main() {
    int day = 3;

    switch (day) {
        case 1:
            printf("月曜日\n");
            break;
        case 2:
            printf("火曜日\n");
            break;
        case 3:
            printf("水曜日\n");
            break;
        default:
            printf("無効な日\n");
    }

    return 0;
}
```

この例では、`day`が3であるため、「水曜日」と表示されます。

## 説明
- **フォールスルー**: `break`文を省略すると、次のcaseも実行されます。これが意図しない動作を引き起こすことがあるため、注意が必要です。
  
```c
switch (day) {
    case 1:
        printf("月曜日\n");
    case 2:
        printf("火曜日\n");
    case 3:
        printf("水曜日\n");
        break;
}
```

この場合、`day`が1のとき、「月曜日」「火曜日」「水曜日」がすべて表示されます。

- **型制限**: `switch`に使用できるのは整数型（int, charなど）や列挙型であり、浮動小数点型や文字列は使用できません。

## 一文要約
C言語の「case」構文は、switch文内で特定の値に基づく条件分岐を簡潔に実装するための機能です。