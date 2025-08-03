<!--
Meta Description: # mktime 函数在 C 语言中的使用 ## 概述 `mktime` 是 C 标准库中的一个函数，用于将结构体 `tm` 表示的时间转换为自纪元（1970年1月1日00:00:00 UTC）以来的秒数。它通常用于时间的计算和转换。 ## 文档 ### 目的 `mktime` 函数的主要目的是将一...
Meta Keywords: mktime, int, timeinfo, struct, 范围从
-->

# mktime 函数在 C 语言中的使用

## 概述
`mktime` 是 C 标准库中的一个函数，用于将结构体 `tm` 表示的时间转换为自纪元（1970年1月1日00:00:00 UTC）以来的秒数。它通常用于时间的计算和转换。

## 文档
### 目的
`mktime` 函数的主要目的是将一个 `struct tm` 结构体中的时间信息转换为 `time_t` 类型的时间戳，以便进行时间的存储和处理。

### 使用方法
函数原型如下：
```c
#include <time.h>

time_t mktime(struct tm *timeptr);
```

#### 参数
- `timeptr`：指向 `struct tm` 结构体的指针，包含了待转换的时间信息。

#### 返回值
- 成功时返回自纪元以来的秒数（`time_t` 类型）。
- 失败时返回 `(time_t)(-1)`，并且会设置 `errno` 以指示错误类型。

### 结构 `tm`
`struct tm` 结构体定义如下：
```c
struct tm {
    int tm_sec;   // 秒，范围从 0 到 60
    int tm_min;   // 分，范围从 0 到 59
    int tm_hour;  // 小时，范围从 0 到 23
    int tm_mday;  // 一个月中的天数，范围从 1 到 31
    int tm_mon;   // 月，范围从 0 到 11
    int tm_year;  // 自 1900 年以来的年份
    int tm_wday;  // 星期几，范围从 0 到 6（0 表示星期天）
    int tm_yday;  // 一年中的天数，范围从 0 到 365
    int tm_isdst; // 夏令时标志
};
```

## 示例
以下是 `mktime` 函数的基本用法示例：

```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo;
    timeinfo.tm_year = 2023 - 1900; // 年份从 1900 开始
    timeinfo.tm_mon = 10 - 1;        // 月份从 0 开始
    timeinfo.tm_mday = 15;           // 日期
    timeinfo.tm_hour = 12;           // 小时
    timeinfo.tm_min = 0;             // 分钟
    timeinfo.tm_sec = 0;             // 秒
    timeinfo.tm_isdst = -1;          // 让系统判断夏令时

    time_t timestamp = mktime(&timeinfo);
    
    if (timestamp != -1) {
        printf("时间戳: %ld\n", timestamp);
    } else {
        perror("mktime 错误");
    }

    return 0;
}
```

## 说明
- **常见问题**：`mktime` 中的 `tm_year` 必须是从 1900 年起的年份，因此需要减去 1900；`tm_mon` 的值范围是 0 到 11。
- **夏令时**：`tm_isdst` 可设为 -1，表示让系统决定是否采用夏令时；或者可以显式指定为 1 或 0。
- **时间范围**：`mktime` 的结果受系统时间范围限制，通常在 1970 年到 2038 年之间。

## 一句话总结
`mktime` 函数用于将 `struct tm` 结构体中的时间信息转换为时间戳，便于时间的计算和处理。