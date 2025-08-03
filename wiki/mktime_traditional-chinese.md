<!--
Meta Description: # mktime 函數在 C 語言中的應用 ## 概述 `mktime` 函數是一個在 C 語言中用來將結構化的時間數據轉換為時間戳的標準庫函數。它提供了一種簡便的方法來處理時間和日期的計算，常用於時間的格式化及比較。 ## 文檔 ### 目的 `mktime` 函數的主要目的是將 `struct ...
Meta Keywords: mktime, timeinfo, struct, 1900, time_t
-->

# mktime 函數在 C 語言中的應用

## 概述
`mktime` 函數是一個在 C 語言中用來將結構化的時間數據轉換為時間戳的標準庫函數。它提供了一種簡便的方法來處理時間和日期的計算，常用於時間的格式化及比較。

## 文檔
### 目的
`mktime` 函數的主要目的是將 `struct tm` 結構中的時間和日期資訊轉換為相對於 1970 年 1 月 1 日的秒數（也稱為 Unix 時間戳）。這對於時間的計算和存儲非常有用。

### 使用方法
`mktime` 函數的原型如下：
```c
time_t mktime(struct tm *timeptr);
```

#### 參數
- `timeptr`: 指向 `struct tm` 結構的指針，該結構包含了需要轉換的時間數據。這個結構中的成員包括：
  - `tm_year`: 自 1900 年以來的年數
  - `tm_mon`: 月份（0 表示一月，11 表示十二月）
  - `tm_mday`: 一個月中的日
  - `tm_hour`: 小時（0 到 23）
  - `tm_min`: 分鐘（0 到 59）
  - `tm_sec`: 秒（0 到 60，考慮到閏秒）
  - `tm_isdst`: 夏令時間標誌（正值表示夏令時間，0 表示不使用，負值表示未確定）

#### 返回值
返回一個 `time_t` 類型的值，表示從 1970 年 1 月 1 日到 `timeptr` 指向的時間的秒數。如果發生錯誤，則返回 -1。

## 示例
以下是一個基本的使用示例：
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo;
    
    // 設定時間為 2023 年 10 月 1 日 12:00:00
    timeinfo.tm_year = 2023 - 1900; // 年份從 1900 開始計算
    timeinfo.tm_mon = 10 - 1;        // 月份從 0 開始計算
    timeinfo.tm_mday = 1;
    timeinfo.tm_hour = 12;
    timeinfo.tm_min = 0;
    timeinfo.tm_sec = 0;
    timeinfo.tm_isdst = -1; // 自動判斷夏令時間

    time_t timestamp = mktime(&timeinfo);
    
    printf("Timestamp: %ld\n", (long)timestamp);
    return 0;
}
```

## 解釋
### 常見陷阱
1. **年份設定錯誤**：記得 `tm_year` 必須是從 1900 年開始的年數，這常常會導致錯誤。
2. **月份範圍**：`tm_mon` 的值範圍是 0 到 11，如果使用 1 到 12 的值，將會導致不正確的計算。
3. **夏令時間**：如果 `tm_isdst` 設為 -1，則 `mktime` 會自動判斷是否使用夏令時間，但如果手動設定，則需要正確設置。

### 附加說明
`mktime` 函數會修改 `struct tm` 結構的內容，以反映可能的調整（如夏令時間的影響）。因此，若需要保持原始數據，應在調用之前複製結構。

## 一句總結
`mktime` 函數是一個強大的工具，用於將結構化的時間數據轉換為 Unix 時間戳，適用於 C 語言中的時間處理。