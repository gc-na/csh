<!--
Meta Description: # C 프로그래밍에서 strstr 함수에 대한 완벽 가이드 ## 개요 `strstr` 함수는 C 언어에서 특정 문자열이 다른 문자열 내에 존재하는지를 찾는 데 사용되는 표준 라이브러리 함수입니다. 이 함수는 문자열 검색 기능을 제공하며, 주로 문자열 처리와 관련된 작업...
Meta Keywords: strstr, needle, 문자열, haystack, 함수는
-->

# C 프로그래밍에서 strstr 함수에 대한 완벽 가이드

## 개요
`strstr` 함수는 C 언어에서 특정 문자열이 다른 문자열 내에 존재하는지를 찾는 데 사용되는 표준 라이브러리 함수입니다. 이 함수는 문자열 검색 기능을 제공하며, 주로 문자열 처리와 관련된 작업에서 널리 사용됩니다.

## 문서화

### 목적
`strstr` 함수는 주어진 문자열 내에서 특정 하위 문자열을 검색하여, 해당 하위 문자열이 처음 나타나는 위치의 포인터를 반환합니다. 만약 하위 문자열이 발견되지 않으면 NULL을 반환합니다.

### 사용법
`strstr` 함수의 기본적인 사용법은 다음과 같습니다:

```c
#include <string.h>

char *strstr(const char *haystack, const char *needle);
```

- **haystack**: 검색할 문자열입니다.
- **needle**: 찾고자 하는 하위 문자열입니다.

### 반환값
- 하위 문자열이 발견되면, 해당 하위 문자열의 첫 번째 문자를 가리키는 포인터를 반환합니다.
- 하위 문자열이 발견되지 않으면 NULL을 반환합니다.

## 예제

### 기본 사용 예제
다음은 `strstr` 함수의 기본적인 사용 예제입니다.

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Hello, World!";
    const char *needle = "World";

    char *result = strstr(haystack, needle);

    if (result != NULL) {
        printf("'%s' found at position: %ld\n", needle, result - haystack);
    } else {
        printf("'%s' not found\n", needle);
    }

    return 0;
}
```

### 출력
```
'World' found at position: 7
```

## 설명

### 일반적인 함정 및 주의 사항
1. **NULL 포인터 처리**: `haystack` 또는 `needle`이 NULL인 경우, `strstr` 함수는 정의되지 않은 동작을 일으킬 수 있습니다. 함수 호출 전에 포인터가 유효한지 확인해야 합니다.
   
2. **대소문자 구분**: `strstr` 함수는 대소문자를 구분합니다. 따라서 "hello"와 "Hello"는 서로 다른 문자열로 간주됩니다.

3. **빈 문자열**: `needle`이 빈 문자열("")인 경우, `strstr`은 항상 `haystack`의 시작 위치를 반환합니다.

4. **성능**: 긴 문자열에서 자주 호출될 경우 성능에 영향을 미칠 수 있습니다. 필요한 경우, 다른 알고리즘을 고려하는 것이 좋습니다.

## 한 줄 요약
`strstr` 함수는 C 언어에서 특정 문자열이 다른 문자열 내에 존재하는지를 찾기 위한 표준 라이브러리 함수로, 발견된 하위 문자열의 첫 번째 위치를 반환합니다.