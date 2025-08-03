<!--
Meta Description: # C에서 strftime 함수: 날짜 및 시간 형식 지정 ## 개요 C 프로그래밍 언어에서 `strftime` 함수는 날짜와 시간을 사용자 지정 형식으로 문자열로 변환하는 기능을 제공합니다. 이 함수는 다양한 날짜 및 시간 형식 지정자를 사용하여 원하는 형식의 문자열...
Meta Keywords: strftime, 함수는, struct, 있습니다, buffer
-->

# C에서 strftime 함수: 날짜 및 시간 형식 지정

## 개요
C 프로그래밍 언어에서 `strftime` 함수는 날짜와 시간을 사용자 지정 형식으로 문자열로 변환하는 기능을 제공합니다. 이 함수는 다양한 날짜 및 시간 형식 지정자를 사용하여 원하는 형식의 문자열을 생성할 수 있습니다.

## 문서화

### 목적
`strftime`은 `struct tm` 구조체에 저장된 날짜 및 시간 정보를 사용하여, 사용자 정의 형식으로 문자열을 생성하는 데 사용됩니다. 이 함수는 주로 날짜 및 시간 출력을 위해 사용됩니다.

### 사용법
```c
#include <time.h>

size_t strftime(char *str, size_t maxsize, const char *format, const struct tm *timeptr);
```

- **str**: 형식화된 날짜 및 시간을 저장할 버퍼의 포인터.
- **maxsize**: 버퍼의 최대 크기.
- **format**: 날짜 및 시간의 형식을 지정하는 문자열.
- **timeptr**: 변환할 날짜 및 시간 정보가 담긴 `struct tm` 구조체의 포인터.

### 반환값
- 성공 시 형식화된 문자열의 길이를 반환합니다.
- 실패 시 0을 반환합니다.

## 예제

### 기본 사용 예제
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    
    char buffer[80];
    strftime(buffer, sizeof(buffer), "%Y-%m-%d %H:%M:%S", tm_info);
    
    printf("현재 날짜와 시간: %s\n", buffer);
    return 0;
}
```

### 결과 예시
```
현재 날짜와 시간: 2023-10-01 14:30:45
```

## 설명

### 일반적인 실수 및 주의 사항
1. **버퍼 크기**: `maxsize`는 반드시 `str` 버퍼의 크기보다 작거나 같아야 합니다. 그렇지 않으면 버퍼 오버플로우가 발생할 수 있습니다.
2. **형식 지정자**: 형식 문자열에 사용할 수 있는 형식 지정자를 잘못 이해하면 예상치 못한 결과가 발생할 수 있습니다. 예를 들어, `%Y`는 연도를 반환하고, `%m`은 월을 반환합니다.
3. **시간대**: `localtime` 함수는 시스템의 로컬 시간대를 기준으로 변환하므로, 시간대에 따라 출력 결과가 달라질 수 있습니다.

## 한 줄 요약
C의 `strftime` 함수는 `struct tm`의 날짜 및 시간 정보를 사용자 정의 형식의 문자열로 변환하는 데 사용됩니다.