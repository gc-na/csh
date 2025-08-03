<!--
Meta Description: # C 프로그래밍 언어의 "break" 명령어 ## 개요 C 프로그래밍 언어에서 "break" 명령어는 루프 또는 switch 문을 조기에 종료하는 데 사용됩니다. 이 명령어는 코드의 흐름을 제어하는 중요한 도구로, 특정 조건을 만족했을 때 반복문을 탈출할 수 있게 해...
Meta Keywords: break, switch, 명령어는, int, printf
-->

# C 프로그래밍 언어의 "break" 명령어

## 개요
C 프로그래밍 언어에서 "break" 명령어는 루프 또는 switch 문을 조기에 종료하는 데 사용됩니다. 이 명령어는 코드의 흐름을 제어하는 중요한 도구로, 특정 조건을 만족했을 때 반복문을 탈출할 수 있게 해줍니다.

## 문서화
"break" 명령어의 주요 목적은 반복문(for, while, do-while) 또는 switch 문을 즉시 종료하는 것입니다. 이 명령어를 사용함으로써 개발자는 더 명확하고 효율적인 코드 흐름을 생성할 수 있습니다.

### 사용법
- **구문**: `break;`
- **위치**: "break" 명령어는 반복문이나 switch 문 내에서 사용되어야 합니다.

### 세부사항
- "break"는 loop의 가장 내부에 있는 블록을 종료합니다.
- "break" 사용 후에는 해당 블록의 모든 코드가 무시되며, 제어는 블록을 감싸고 있는 다음 문으로 이동합니다.
- switch 문에서 "break"가 없으면 다음 case로 계속 진행하게 됩니다.

## 예제
다음은 "break" 명령어의 기본 사용법을 보여주는 간단한 예제입니다.

### 예제 1: for 루프에서의 사용
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break; // i가 5일 때 루프 종료
        }
        printf("%d ", i);
    }
    return 0;
}
```
**출력**: `0 1 2 3 4 `

### 예제 2: switch 문에서의 사용
```c
#include <stdio.h>

int main() {
    int num = 2;

    switch (num) {
        case 1:
            printf("One\n");
            break; // case 1 종료
        case 2:
            printf("Two\n");
            break; // case 2 종료
        default:
            printf("Default\n");
    }
    return 0;
}
```
**출력**: `Two`

## 설명
"break" 명령어는 강력한 도구이지만, 사용 시 몇 가지 주의할 점이 있습니다.
- **중첩된 루프**: "break"는 가장 가까운 루프만 종료하므로, 중첩된 루프에서 사용 시 어떤 루프가 종료되는지 명확히 이해하고 있어야 합니다.
- **switch 문에서의 연속성**: "break" 문이 없으면 다음 case로 이어지기 때문에, 의도하지 않은 동작을 유발할 수 있습니다.
- **가독성**: "break"를 남용하면 코드의 가독성이 떨어질 수 있으므로, 필요한 경우에만 사용하는 것이 좋습니다.

## 한 줄 요약
C 언어에서 "break" 명령어는 루프나 switch 문을 조기에 종료하는 데 사용됩니다.