<!--
Meta Description: # C 프로그래밍 언어의 perror 함수: 에러 메시지 출력하기 ## 개요 `perror` 함수는 C 프로그래밍에서 오류 메시지를 출력하는 데 사용됩니다. 이 함수는 파일 입출력 및 시스템 호출과 같은 다양한 작업에서 발생하는 오류를 사용자에게 안내하는 데 유용합니다...
Meta Keywords: perror, 메시지를, errno, include, 함수는
-->

# C 프로그래밍 언어의 perror 함수: 에러 메시지 출력하기

## 개요
`perror` 함수는 C 프로그래밍에서 오류 메시지를 출력하는 데 사용됩니다. 이 함수는 파일 입출력 및 시스템 호출과 같은 다양한 작업에서 발생하는 오류를 사용자에게 안내하는 데 유용합니다.

## 문서화

### 목적
`perror` 함수는 전역 변수인 `errno`의 값을 기반으로 오류 메시지를 생성하여 출력합니다. `errno`는 시스템 호출이나 라이브러리 함수가 실패할 경우 설정되는 오류 코드를 담고 있습니다.

### 사용법
`perror` 함수의 기본 구문은 다음과 같습니다:

```c
#include <stdio.h>
#include <string.h>
#include <errno.h>

void perror(const char *s);
```

- `s`: 출력할 메시지의 접두사로 사용됩니다. 이 문자열은 오류 메시지 앞에 출력됩니다. 만약 `s`가 NULL이면 기본 메시지만 출력됩니다.

### 반환값
`perror` 함수는 반환값이 없으며, 단순히 표준 오류 출력(`stderr`)에 메시지를 출력합니다.

## 예제

### 기본 사용 예제

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *file = fopen("nonexistent.txt", "r");
    if (file == NULL) {
        perror("파일 열기 실패");
        exit(EXIT_FAILURE);
    }
    fclose(file);
    return 0;
}
```

위의 예제에서, 존재하지 않는 파일을 열려고 시도합니다. 파일 열기에 실패하면 `perror`가 "파일 열기 실패: "라는 메시지를 출력하고 뒤따르는 시스템 오류 메시지를 보여줍니다.

### `perror` 사용 예제

```c
#include <stdio.h>
#include <string.h>
#include <errno.h>

int main() {
    errno = ENOENT; // 존재하지 않는 파일 오류 설정
    perror("오류 발생");
    return 0;
}
```

이 예제에서는 `errno`를 직접 설정한 후 `perror`를 호출하여 "오류 발생: No such file or directory"와 같은 메시지를 출력합니다.

## 설명

### 일반적인 문제점
- `perror`가 출력하는 메시지는 `errno`가 세트되어 있어야 합니다. 그렇지 않으면 기본 메시지가 출력되지 않을 수 있습니다.
- `perror`는 스레드 안전하지 않으므로 멀티스레드 환경에서는 주의가 필요합니다.

### 추가 노트
- `perror`는 사용자 지정 오류 메시지를 제공할 수 있는 좋은 방법입니다. 이를 통해 사용자는 문제의 원인을 쉽게 파악할 수 있습니다.
- `strerror(errno)` 함수와 유사하지만, `perror`는 메시지를 자동으로 출력하고 `stderr`에 직접 보냅니다.

## 한 줄 요약
`perror` 함수는 C에서 오류 메시지를 출력하여 문제를 쉽게 파악할 수 있게 도와주는 유용한 도구입니다.