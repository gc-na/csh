<!--
Meta Description: # C에서 mktime 함수에 대한 완벽한 가이드 ## 개요 `mktime` 함수는 C 언어의 시간 관련 함수 중 하나로, 구조체 `tm`을 사용하여 로컬 시간으로 변환된 시간 값을 반환합니다. 이 함수는 날짜와 시간을 정수형 데이터로 처리할 때 유용합니다. ## 문서...
Meta Keywords: mktime, struct, timeinfo, 함수는, time
-->

# C에서 mktime 함수에 대한 완벽한 가이드

## 개요
`mktime` 함수는 C 언어의 시간 관련 함수 중 하나로, 구조체 `tm`을 사용하여 로컬 시간으로 변환된 시간 값을 반환합니다. 이 함수는 날짜와 시간을 정수형 데이터로 처리할 때 유용합니다.

## 문서화
### 목적
`mktime` 함수는 `struct tm` 구조체에 저장된 날짜 및 시간을 UNIX 시간(1970년 1월 1일 00:00:00 UTC부터의 초)으로 변환합니다. 이 함수는 주로 날짜 및 시간 계산, 비교 및 출력에 사용됩니다.

### 사용법
```c
#include <time.h>

time_t mktime(struct tm *timeptr);
```

- **매개변수**: 
  - `timeptr`: 변환할 날짜와 시간이 저장된 `struct tm` 포인터. 이 구조체는 연도, 월, 일, 시, 분, 초 등의 정보를 포함합니다.

- **반환값**: 
  - 변환된 `time_t` 형식의 시간 값. 변환이 실패할 경우 `-1`을 반환합니다.

### 세부사항
- `struct tm`의 필드:
  - `tm_year`: 연도 - 1900을 더한 값
  - `tm_mon`: 월 - 0부터 11까지 (0=1월, 11=12월)
  - `tm_mday`: 일 - 1부터 31까지
  - `tm_hour`: 시 - 0부터 23까지
  - `tm_min`: 분 - 0부터 59까지
  - `tm_sec`: 초 - 0부터 60까지 (윤초를 고려)

- `mktime` 함수는 `struct tm`의 필드가 유효한 범위 내에 있는지 확인하며, 올바른 범위가 아닐 경우 `-1`을 반환할 수 있습니다.

## 예제
### 기본 사용 예
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo = {0};
    timeinfo.tm_year = 2023 - 1900; // 2023년
    timeinfo.tm_mon = 10 - 1; // 10월
    timeinfo.tm_mday = 15; // 15일
    timeinfo.tm_hour = 12; // 12시
    timeinfo.tm_min = 30; // 30분
    timeinfo.tm_sec = 0; // 0초

    time_t time = mktime(&timeinfo);
    if (time != -1) {
        printf("변환된 시간: %ld\n", time);
    } else {
        printf("시간 변환 실패\n");
    }

    return 0;
}
```

## 설명
- **일반적인 오류**: 
  - `struct tm`의 필드 값이 유효한 범위를 넘어서면 `mktime`은 `-1`을 반환합니다. 예를 들어, 월이 12보다 크거나, 날이 31일보다 큰 경우가 이에 해당합니다.
  
- **윤초 처리**: 
  - `tm_sec` 필드가 60일 경우, 이는 윤초를 나타내며 `mktime`은 이를 적절히 처리합니다.

- **로컬 시간**: 
  - `mktime`은 시스템의 로컬 시간대에 따라 결과를 반환하므로, UTC 시간으로 변환이 필요할 경우 추가적인 처리가 필요할 수 있습니다.

## 한 줄 요약
`mktime` 함수는 `struct tm` 구조체를 로컬 시간으로 변환하여 `time_t` 형식의 시간을 반환하는 C 언어의 유용한 시간 처리 함수입니다.