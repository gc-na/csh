<!--
Meta Description: # C言語における「default」 ## 概要 C言語における「default」は、主にswitch文の中で使われるキーワードです。このキーワードは、指定されたcaseに一致しない場合に実行されるコードブロックを定義します。 ## ドキュメント 「default」キーワードは、switch文の一部...
Meta Keywords: break, case, default, printf, c言語における
-->

# C言語における「default」

## 概要
C言語における「default」は、主にswitch文の中で使われるキーワードです。このキーワードは、指定されたcaseに一致しない場合に実行されるコードブロックを定義します。

## ドキュメント
「default」キーワードは、switch文の一部として使用され、特定の条件が満たされない場合に代替の処理を提供します。switch文は、複数の条件を簡潔に処理するための便利な構文です。defaultはオプションですが、caseにマッチしないすべての状況をカバーするために重要です。

### 目的
- 条件に一致しない場合の処理を指定する。
- コードの可読性を向上させる。

### 使用法
defaultセクションは、switch文の最後に配置されることが一般的です。以下は基本的な構文です。

```c
switch (変数) {
    case 値1:
        // 値1に対する処理
        break;
    case 値2:
        // 値2に対する処理
        break;
    default:
        // どのcaseにも一致しない場合の処理
        break;
}
```

## 例
以下は、switch文におけるdefaultの基本的な使用例です。

```c
#include <stdio.h>

int main() {
    int day = 5;

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
        case 4:
            printf("木曜日\n");
            break;
        case 5:
            printf("金曜日\n");
            break;
        default:
            printf("週末です\n");
            break;
    }

    return 0;
}
```

この例では、変数dayが5の場合、プログラムは「金曜日」と出力します。もしdayが1から5のいずれにも該当しない場合、defaultが実行され「週末です」と出力されます。

## 説明
defaultセクションは、switch文で指定されたcaseに一致しない場合に実行されるため、すべての可能性をカバーするために重要です。以下のような一般的な注意点があります。

- defaultはオプションですが、caseが全ての可能性をカバーしていない場合は、defaultを追加することをお勧めします。
- case文とdefault文の間にbreak文を含めることを忘れないでください。そうしないと、次のcaseに流れ込むフォールスルーが発生します。

## 一文要約
C言語における「default」は、switch文内で指定されたcaseに一致しない場合に実行される処理を定義するためのキーワードです。