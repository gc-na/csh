<!--
Meta Description: # C 언어의 switch 문: 사용법 및 예제 ## 개요 C 언어의 switch 문은 여러 조건을 비교하여 특정 값에 따라 실행할 코드를 선택하는 제어 구조입니다. 이를 통해 복잡한 if-else 문을 대체할 수 있으며, 가독성을 높이고 코드의 효율성을 증대시킬 수 ...
Meta Keywords: case, break, switch, printf, 실행할
-->

# C 언어의 switch 문: 사용법 및 예제

## 개요
C 언어의 switch 문은 여러 조건을 비교하여 특정 값에 따라 실행할 코드를 선택하는 제어 구조입니다. 이를 통해 복잡한 if-else 문을 대체할 수 있으며, 가독성을 높이고 코드의 효율성을 증대시킬 수 있습니다.

## 문서화

### 목적
switch 문은 특정 변수의 값을 검사하고, 그 값에 따라 코드 블록을 실행하는 데 사용됩니다. 이는 복잡한 조건문보다 코드의 가독성을 높이는 데 유용합니다.

### 사용법
switch 문은 다음과 같은 형식을 가지고 있습니다:

```c
switch (expression) {
    case constant1:
        // 실행할 코드
        break;
    case constant2:
        // 실행할 코드
        break;
    // 추가적인 case 문
    default:
        // 모든 case에 해당하지 않을 때 실행할 코드
}
```

- **expression**: 평가할 변수 또는 표현식입니다.
- **case constant**: expression의 값이 constant와 일치할 때 실행할 코드입니다.
- **break**: 현재 case 블록을 종료하고 switch 문을 빠져나갑니다. break 문이 없으면 다음 case로 넘어갑니다.
- **default**: 모든 case에 해당하지 않는 경우 실행되는 코드입니다. 선택 사항입니다.

## 예제

### 기본 사용 예제
다음은 switch 문을 사용하여 숫자에 따라 요일을 출력하는 간단한 프로그램입니다.

```c
#include <stdio.h>

int main() {
    int day = 3;

    switch (day) {
        case 1:
            printf("월요일\n");
            break;
        case 2:
            printf("화요일\n");
            break;
        case 3:
            printf("수요일\n");
            break;
        case 4:
            printf("목요일\n");
            break;
        case 5:
            printf("금요일\n");
            break;
        case 6:
            printf("토요일\n");
            break;
        case 7:
            printf("일요일\n");
            break;
        default:
            printf("유효하지 않은 날입니다.\n");
    }

    return 0;
}
```

## 설명

### 흔히 발생하는 실수 및 주의사항
- **break 문 누락**: break 문이 없으면 다음 case로 자동으로 넘어가기 때문에 의도하지 않은 코드가 실행될 수 있습니다.
- **중복 case 상수**: 동일한 상수가 여러 case에 존재하면 컴파일 오류가 발생합니다.
- **정수형과 문자형**: switch 문은 정수형, 문자형과 같은 기본 데이터 타입에 적합하지만, 문자열이나 부동 소수점 수와 같은 데이터 타입은 지원하지 않습니다.
- **default 문**: default 문은 선택 사항이지만, 모든 case가 일치하지 않을 경우를 대비하여 포함하는 것이 좋습니다.

## 한 줄 요약
C 언어의 switch 문은 주어진 표현식의 값에 따라 여러 실행 경로를 선택할 수 있는 효율적인 제어 구조입니다.