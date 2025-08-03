<!--
Meta Description: # C에서의 _Bool 타입: 부울 데이터 타입에 대한 모든 것 ## 개요 C 프로그래밍 언어에서 `_Bool`은 논리적 참(True)과 거짓(False)을 표현하기 위한 데이터 타입입니다. C99 표준에서 도입된 이 타입은 불리언 연산을 보다 명확하고 안전하게 수행할...
Meta Keywords: _bool, stdbool, 데이터, false, bool
-->

# C에서의 _Bool 타입: 부울 데이터 타입에 대한 모든 것

## 개요
C 프로그래밍 언어에서 `_Bool`은 논리적 참(True)과 거짓(False)을 표현하기 위한 데이터 타입입니다. C99 표준에서 도입된 이 타입은 불리언 연산을 보다 명확하고 안전하게 수행할 수 있도록 해줍니다.

## 문서화
`_Bool`은 C 언어의 기본 데이터 타입 중 하나로, 0은 거짓을, 0이 아닌 값은 참을 의미합니다. C99 표준에서는 `stdbool.h` 헤더 파일을 통해 `bool`이라는 별칭을 제공하여 `_Bool`을 보다 직관적으로 사용할 수 있도록 지원합니다. `_Bool` 타입은 메모리에서 1바이트를 차지하며, 다음과 같은 주요 특징이 있습니다:

- **값**: `_Bool` 변수는 0 또는 1의 값을 가질 수 있습니다. 
- **형 변환**: 다른 정수 타입에서 `_Bool`으로의 변환 시, 0은 거짓으로 변환되고, 0이 아닌 모든 값은 참으로 변환됩니다.
- **사용 편의성**: `stdbool.h`를 포함하면 `bool`, `true`, `false` 같은 키워드를 사용할 수 있어 코드의 가독성이 향상됩니다.

### 사용법
`_Bool` 타입을 사용하기 위해서는 특별한 선언이 필요하지 않습니다. 아래의 코드를 참고하세요:

```c
#include <stdio.h>
#include <stdbool.h>

int main() {
    _Bool flag = 1; // 참
    bool isActive = false; // 거짓

    printf("flag: %d\n", flag); // 1 출력
    printf("isActive: %d\n", isActive); // 0 출력

    return 0;
}
```

## 예제
아래는 `_Bool` 타입을 사용하는 간단한 코드 예제입니다.

```c
#include <stdio.h>
#include <stdbool.h>

int main() {
    _Bool isEven(int num) {
        return num % 2 == 0;
    }

    int number = 4;
    if (isEven(number)) {
        printf("%d은 짝수입니다.\n", number);
    } else {
        printf("%d은 홀수입니다.\n", number);
    }

    return 0;
}
```

## 설명
- `_Bool` 사용 시 주의할 점은 C 언어의 특성상 0이 아닌 모든 값이 참으로 변환된다는 것입니다. 예를 들어, -1, 2, 3 등은 모두 참으로 평가됩니다.
- 또한, `_Bool` 변수는 기본적으로 0 또는 1만 가질 수 있지만, 다른 정수형 데이터에서 변환 시 의도하지 않은 결과를 초래할 수 있으므로 주의해야 합니다.
- `stdbool.h`를 포함하면 `bool`, `true`, `false` 키워드를 사용할 수 있어 가독성이 높아지므로, C99 이상에서는 이 헤더를 포함하는 것이 좋습니다.

## 한 줄 요약
`_Bool`은 C에서 논리적 참과 거짓을 표현하기 위해 사용되는 데이터 타입으로, 0은 거짓, 0이 아닌 값은 참으로 간주됩니다.