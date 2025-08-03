<!--
Meta Description: # C 프로그래밍에서의 extern 키워드 ## 개요 C 프로그래밍 언어에서 `extern` 키워드는 변수나 함수의 정의가 다른 파일에 존재함을 명시하는 데 사용됩니다. 이를 통해 여러 소스 파일 간의 데이터 공유가 가능해집니다. ## 문서 `extern` 키워드는 주...
Meta Keywords: extern, 파일에서, globalvar, 사용할, 변수나
-->

# C 프로그래밍에서의 extern 키워드

## 개요
C 프로그래밍 언어에서 `extern` 키워드는 변수나 함수의 정의가 다른 파일에 존재함을 명시하는 데 사용됩니다. 이를 통해 여러 소스 파일 간의 데이터 공유가 가능해집니다.

## 문서
`extern` 키워드는 주로 변수나 함수의 외부 링크를 선언할 때 사용됩니다. 이 키워드를 사용하면, 해당 변수나 함수가 다른 파일에서 정의되어 있음을 컴파일러에 알릴 수 있습니다. 이를 통해 전역 변수를 여러 파일에서 사용할 수 있으며, 같은 이름의 변수를 여러 파일에 정의할 때 발생할 수 있는 충돌을 방지할 수 있습니다.

### 사용법
- **변수 선언**: `extern`을 사용하여 다른 파일에서 정의된 전역 변수를 사용할 수 있습니다.
- **함수 선언**: `extern`은 함수의 외부 링크를 명시적으로 나타내기도 하지만, 기본적으로 함수는 외부 링크가 기본이므로 종종 생략합니다.

### 예제
```c
// file1.c
#include <stdio.h>

int globalVar = 10; // 전역 변수 정의

void displayVar() {
    printf("Global Variable: %d\n", globalVar);
}

// file2.c
#include <stdio.h>

extern int globalVar; // 외부 전역 변수 선언

void changeVar() {
    globalVar = 20; // file1.c의 globalVar 변경
}

int main() {
    displayVar(); // file1.c의 displayVar 함수 호출
    changeVar(); // file2.c의 changeVar 함수 호출
    displayVar(); // 변경된 globalVar 출력
    return 0;
}
```

## 설명
`extern` 키워드를 사용할 때 주의해야 할 점은 다음과 같습니다:
- `extern`으로 선언된 변수는 반드시 다른 파일에서 정의되어야 하며, 그렇지 않으면 링커 오류가 발생합니다.
- `extern`은 기본적으로 함수에 대해 생략 가능하지만, 코드의 가독성을 높이기 위해 명시적으로 사용할 수 있습니다.
- 여러 파일에서 동일한 변수를 사용할 때, 각 파일에서 `extern`으로 선언하고 실제 정의는 한 파일에서만 해야 합니다.

## 한 줄 요약
`extern` 키워드는 C에서 변수나 함수의 외부 링크를 선언하여 여러 소스 파일 간의 데이터 공유를 가능하게 하는 키워드입니다.