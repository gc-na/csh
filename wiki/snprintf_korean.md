<!--
Meta Description: # C 언어의 snprintf 함수: 안전한 문자열 포맷팅 ## 개요 `snprintf`는 C 언어에서 문자열을 안전하게 포맷팅하고 출력하기 위해 사용되는 함수로, 버퍼 오버플로우를 방지하는 동시에 지정된 크기 내에서 문자열을 생성합니다. ## 문서화 ### 목적 `s...
Meta Keywords: snprintf, buffer, 문자열을, 버퍼의, int
-->

# C 언어의 snprintf 함수: 안전한 문자열 포맷팅

## 개요
`snprintf`는 C 언어에서 문자열을 안전하게 포맷팅하고 출력하기 위해 사용되는 함수로, 버퍼 오버플로우를 방지하는 동시에 지정된 크기 내에서 문자열을 생성합니다.

## 문서화

### 목적
`snprintf` 함수는 지정된 버퍼에 포맷된 문자열을 작성하며, 버퍼의 크기를 지정할 수 있어 안전성을 높입니다. 이는 특히 사용자 입력이나 외부 데이터를 처리할 때 중요합니다.

### 사용법
```c
#include <stdio.h>

int snprintf(char *str, size_t size, const char *format, ...);
```

- **str**: 포맷된 문자열을 저장할 버퍼.
- **size**: 버퍼의 크기.
- **format**: 포맷 문자열.
- **...**: 추가 인수 (포맷 문자열에 따라 다름).

### 반환값
- 성공적으로 작성된 문자열의 길이를 반환합니다. 만약 버퍼의 크기를 초과한다면, 실제 작성된 문자열의 길이를 반환하되, 버퍼에는 null 문자로 종료되지 않을 수 있습니다.

## 예제

### 기본 사용 예제
```c
#include <stdio.h>

int main() {
    char buffer[50];
    int n = snprintf(buffer, sizeof(buffer), "Hello %s!", "World");
    
    printf("Formatted String: %s\n", buffer);
    printf("Number of characters that would be written: %d\n", n);
    
    return 0;
}
```

### 버퍼 크기 초과 예제
```c
#include <stdio.h>

int main() {
    char buffer[10];
    int n = snprintf(buffer, sizeof(buffer), "Hello, World!");

    printf("Formatted String: %s\n", buffer); // 출력: "Hello, Wo"
    printf("Number of characters that would be written: %d\n", n); // 실제 길이 13
    
    return 0;
}
```

## 설명

### 일반적인 실수 및 주의사항
- **버퍼 크기 확인**: `snprintf`를 사용할 때는 항상 버퍼의 크기를 확인해야 합니다. 만약 버퍼의 크기가 충분하지 않으면 데이터가 잘리거나 null 종료가 되지 않을 수 있습니다.
  
- **반환값 활용**: 반환값을 통해 작성된 문자열의 길이를 체크하면, 오류를 방지하고 디버깅에 도움이 됩니다.

- **서식 문자열**: 서식 문자열에서 지정한 타입에 맞지 않는 인수를 제공하면, 예기치 않은 결과를 초래할 수 있습니다. 따라서 항상 올바른 타입의 인수를 제공해야 합니다.

- **C11 표준**: C11부터는 `snprintf`의 보장된 동작이 개선되었습니다. 그 이전의 버전에서는 특정 상황에서 동작이 다를 수 있습니다.

## 한 줄 요약
`snprintf`는 C 언어에서 안전하게 문자열을 포맷팅하고 출력하기 위해 사용되는 함수로, 버퍼 크기를 지정함으로써 메모리 안전성을 제공합니다.