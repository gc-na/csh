<!--
Meta Description: # C 프로그래밍 언어에서의 "default" 키워드 ## 개요 C 프로그래밍 언어에서 "default" 키워드는 switch 문에서 사용되며, 특정 조건이 충족되지 않을 경우 실행될 코드를 정의합니다. 이 기능은 코드의 가독성을 높이고, 다양한 경우를 처리하는 데 유...
Meta Keywords: default, switch, break, case, number
-->

# C 프로그래밍 언어에서의 "default" 키워드

## 개요
C 프로그래밍 언어에서 "default" 키워드는 switch 문에서 사용되며, 특정 조건이 충족되지 않을 경우 실행될 코드를 정의합니다. 이 기능은 코드의 가독성을 높이고, 다양한 경우를 처리하는 데 유용합니다.

## 문서화
### 목적
"Default"는 switch 문에서 모든 case가 해당하지 않을 때 실행되는 블록을 정의하는 데 사용됩니다. 이는 코드의 흐름을 보다 명확하게 하고, 예외적 경우를 처리할 수 있는 방법을 제공합니다.

### 사용법
"Default" 키워드는 switch 문 내에서 사용되며, 다른 case 문과 함께 정의됩니다. 기본적인 문법은 다음과 같습니다:

```c
switch (expression) {
    case constant1:
        // code block
        break;
    case constant2:
        // code block
        break;
    default:
        // code block
}
```

### 세부사항
- **위치**: "default" 블록은 case 블록 후에 위치해야 하며, 선택적으로 switch 문 내의 마지막에 배치될 수 있습니다.
- **break 문**: 지정된 코드 블록이 실행된 후, "break" 문을 사용하여 switch 문을 종료할 수 있습니다. 만약 "break"가 없다면, 다음 case로 "fall through" 됩니다.
- **선택적 사용**: "default"는 필수가 아니며, 모든 case가 처리된 후의 동작이 필요할 경우에만 사용합니다.

## 예제
아래는 "default" 키워드를 사용하는 간단한 예제입니다:

```c
#include <stdio.h>

int main() {
    int num = 2;

    switch (num) {
        case 1:
            printf("Number is one.\n");
            break;
        case 2:
            printf("Number is two.\n");
            break;
        default:
            printf("Number is neither one nor two.\n");
    }

    return 0;
}
```

이 코드에서, 변수 `num`의 값이 2일 경우 "Number is two."가 출력됩니다. 만약 `num`의 값이 1 또는 2가 아닐 경우, "Number is neither one nor two."가 출력됩니다.

## 설명
- **일치하지 않는 경우 처리**: "default" 블록이 없으면, 모든 case가 해당하지 않았을 때 발생할 수 있는 오류를 방지할 수 있습니다.
- **다양한 데이터 타입**: switch 문에서는 정수형 및 문자형 변수를 사용할 수 있지만, float나 double과 같은 실수형 변수는 사용할 수 없습니다. 이 점을 유의해야 합니다.
- **가독성**: "default" 사용은 코드의 가독성을 높이고, 유지보수를 용이하게 합니다.

## 한 줄 요약
C 언어에서 "default" 키워드는 switch 문에 사용되어 모든 case가 해당하지 않을 때 실행될 코드를 정의합니다.