<!--
Meta Description: # strftime：C 語言中的日期時間格式化函數 ## 簡介 `strftime` 是 C 語言中用來格式化日期和時間的函數。它能夠將結構化的時間數據轉換成可讀的字符串格式，便於用戶進行顯示或存儲。 ## 文檔 `strftime` 函數的主要功能是根據指定的格式字符串將 `struct tm`...
Meta Keywords: strftime, str, struct, buffer, time
-->

# strftime：C 語言中的日期時間格式化函數

## 簡介
`strftime` 是 C 語言中用來格式化日期和時間的函數。它能夠將結構化的時間數據轉換成可讀的字符串格式，便於用戶進行顯示或存儲。

## 文檔
`strftime` 函數的主要功能是根據指定的格式字符串將 `struct tm` 結構中的時間數據格式化為字符串。其原型定義在 `<time.h>` 標頭文件中：

```c
size_t strftime(char *str, size_t maxsize, const char *format, const struct tm *timeptr);
```

### 參數說明
- **str**: 指向將要存儲格式化日期時間字符串的字符數組的指針。
- **maxsize**: `str` 能夠容納的最大字符數。
- **format**: 用來指示日期時間格式的格式字符串。
- **timeptr**: 指向 `struct tm` 結構的指針，該結構包含待格式化的時間信息。

### 返回值
`strftime` 返回實際寫入 `str` 的字符數，如果無法寫入，則返回 0。

### 格式化選項
格式字符串中可以包含各種格式化標記，例如：
- `%Y`: 四位年份
- `%m`: 月份（01-12）
- `%d`: 日期（01-31）
- `%H`: 小時（00-23）
- `%M`: 分鐘（00-59）
- `%S`: 秒（00-59）

## 例子
以下是一個使用 `strftime` 的基本例子：

```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm tm = *localtime(&t);
    
    char buffer[80];
    strftime(buffer, sizeof(buffer), "現在是 %Y-%m-%d %H:%M:%S", &tm);
    
    printf("%s\n", buffer);
    return 0;
}
```

在這個例子中，程序將當前的日期和時間格式化為 `YYYY-MM-DD HH:MM:SS` 的格式並輸出。

## 解釋
使用 `strftime` 時需要注意以下幾點：
- 確保 `str` 的大小足夠，否則可能導致溢出錯誤。
- 格式字符串中不支持的格式化標記會被忽略。
- 若返回值為 0，則表示格式化失敗，應檢查 `maxsize` 是否足夠大。

## 總結
`strftime` 是一個強大且靈活的函數，用於將 C 語言中的時間數據格式化為可讀字符串。