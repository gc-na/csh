<!--
Meta Description: # C의 strcmp 함수: 문자열 비교의 기초 ## 개요 `strcmp` 함수는 C 프로그래밍 언어에서 문자열을 비교하는 데 사용되는 표준 라이브러리 함수입니다. 두 문자열의 사전적 순서를 비교하여 그 결과를 정수 값으로 반환합니다. ## 문서화 ### 목적 `str...
Meta Keywords: strcmp, str1, 함수는, const, char
-->

# C의 strcmp 함수: 문자열 비교의 기초

## 개요
`strcmp` 함수는 C 프로그래밍 언어에서 문자열을 비교하는 데 사용되는 표준 라이브러리 함수입니다. 두 문자열의 사전적 순서를 비교하여 그 결과를 정수 값으로 반환합니다.

## 문서화
### 목적
`strcmp` 함수는 두 개의 문자열을 비교하여 다음과 같은 결과를 제공합니다:
- 0: 두 문자열이 동일한 경우
- 음수: 첫 번째 문자열이 두 번째 문자열보다 사전적으로 앞서는 경우
- 양수: 첫 번째 문자열이 두 번째 문자열보다 사전적으로 뒤서는 경우

### 사용법
`strcmp` 함수는 다음과 같이 선언됩니다:

```c
int strcmp(const char *str1, const char *str2);
```

- `str1`: 비교할 첫 번째 문자열
- `str2`: 비교할 두 번째 문자열

함수는 두 문자열을 비교한 결과를 정수로 반환합니다.

### 세부사항
- 문자열 비교는 ASCII 값에 기반하여 이루어집니다.
- 대소문자를 구분하여 비교합니다. 즉, "abc"와 "ABC"는 서로 다른 문자열로 인식됩니다.
- NULL 포인터를 전달할 경우, 정의되지 않은 동작이 발생할 수 있으므로 주의해야 합니다.

## 예제
다음은 `strcmp` 함수의 기본적인 사용 예입니다.

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hello";
    const char *str2 = "World";
    const char *str3 = "Hello";

    int result1 = strcmp(str1, str2);
    int result2 = strcmp(str1, str3);

    printf("Comparison of '%s' and '%s': %d\n", str1, str2, result1); // 음수 출력
    printf("Comparison of '%s' and '%s': %d\n", str1, str3, result2); // 0 출력

    return 0;
}
```

## 설명
`strcmp` 사용 시 주의해야 할 점은 다음과 같습니다:
- 대소문자를 구분하므로 사용할 때 주의가 필요합니다. 예를 들어, "abc"와 "ABC"는 서로 다르게 평가됩니다.
- NULL 문자열과의 비교는 정의되지 않은 동작을 초래할 수 있습니다. 따라서 문자열이 NULL인지 확인 후 비교하는 것이 좋습니다.
- 문자열의 길이가 다르더라도 내용이 같다면 그 결과는 0이 아닙니다.

## 한 줄 요약
`strcmp` 함수는 두 문자열을 비교하여 사전적 순서를 반환하는 C 표준 라이브러리 함수입니다.