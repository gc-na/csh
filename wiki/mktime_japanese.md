<!--
Meta Description: # C言語の「mktime」関数：日付と時刻の変換 ## 概要 「mktime」は、C言語において構造体tmを使って表現された日付と時刻を、カレンダー時間（time_t型）に変換するための関数です。この関数を使用することで、日付の計算やタイムゾーンの調整が容易になります。 ## ドキュメント ###...
Meta Keywords: timeinfo, mktime, rawtime, include, time_t型
-->

# C言語の「mktime」関数：日付と時刻の変換

## 概要
「mktime」は、C言語において構造体tmを使って表現された日付と時刻を、カレンダー時間（time_t型）に変換するための関数です。この関数を使用することで、日付の計算やタイムゾーンの調整が容易になります。

## ドキュメント
### 目的
「mktime」関数は、tm構造体を使って指定された日付と時刻をUnix時間（1970年1月1日からの秒数）に変換します。この関数は、日付の操作や比較に役立ちます。

### 使用方法
```c
#include <time.h>

time_t mktime(struct tm *timeptr);
```

#### 引数
- `timeptr`: 変換したい日付と時刻を持つtm構造体へのポインタ。

#### 戻り値
- 成功した場合、Unix時間（time_t型）を返します。失敗した場合は、-1を返します。

### 詳細
`tm`構造体には、年、月、日、時、分、秒などの情報が含まれています。`mktime`は、これらの情報をもとに、適切な時間を計算します。月は0から11までの値で表現されるため、注意が必要です。

## 例
以下に「mktime」の基本的な使用例を示します。

```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo;
    time_t rawtime;

    // 日付を設定（2023年10月1日 12:00:00）
    timeinfo.tm_year = 2023 - 1900; // 年は1900年からのオフセット
    timeinfo.tm_mon = 9; // 10月（0から始まる）
    timeinfo.tm_mday = 1;
    timeinfo.tm_hour = 12;
    timeinfo.tm_min = 0;
    timeinfo.tm_sec = 0;
    timeinfo.tm_isdst = -1; // デイライトセービングタイムの自動調整を指示

    // mktimeを使って変換
    rawtime = mktime(&timeinfo);
    
    if (rawtime != -1) {
        printf("Unix時間: %ld\n", rawtime);
    } else {
        printf("エラー: 日付の変換に失敗しました。\n");
    }

    return 0;
}
```

## 説明
- **共通の落とし穴**: `tm`構造体のフィールドに正しい値をセットする必要があります。特に`tm_year`は1900年からのオフセットであるため、注意が必要です。また、`tm_mon`は0から始まるため、1月は0、2月は1というように設定します。
- **DSTの扱い**: `tm_isdst`フィールドを-1に設定すると、システムが自動的にデイライトセービングタイムを調整します。適切に設定しないと、期待通りの結果が得られない可能性があります。

## 一文要約
「mktime」は、tm構造体で表現された日付と時刻をUnix時間に変換するC言語の関数です。