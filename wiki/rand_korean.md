<!--
Meta Description: # C 언어의 rand 함수: 난수 생성자를 활용한 무작위 수 생성 ## 개요 C 언어의 `rand()` 함수는 의사 난수를 생성하는 기능을 제공합니다. 이 함수는 주로 게임, 시뮬레이션, 통계적 샘플링 등 다양한 분야에서 무작위 수를 필요로 할 때 사용됩니다. ## ...
Meta Keywords: rand, int, include, 함수는, random_number
-->

# C 언어의 rand 함수: 난수 생성자를 활용한 무작위 수 생성

## 개요
C 언어의 `rand()` 함수는 의사 난수를 생성하는 기능을 제공합니다. 이 함수는 주로 게임, 시뮬레이션, 통계적 샘플링 등 다양한 분야에서 무작위 수를 필요로 할 때 사용됩니다.

## 문서화

### 목적
`rand()` 함수는 0과 `RAND_MAX` 사이의 무작위 정수를 반환합니다. `RAND_MAX`는 `stdlib.h` 헤더 파일에 정의되어 있으며, 시스템에 따라 다르지만 일반적으로 32767로 설정됩니다. 이 함수는 반복적으로 호출할 때마다 다른 값을 반환하도록 설계되었습니다.

### 사용법
`rand()` 함수를 사용하기 위해서는 먼저 `stdlib.h` 헤더 파일을 포함해야 합니다. 기본 사용법은 다음과 같습니다:

```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    int random_number = rand();
    printf("Generated Random Number: %d\n", random_number);
    return 0;
}
```

### 상세 정보
- **시드 설정**: `rand()` 함수는 시드 값에 따라 생성하는 난수의 패턴이 결정됩니다. 기본적으로 `rand()`는 같은 시드 값으로 초기화되면 매번 동일한 난수를 생성합니다. 이를 방지하기 위해 `srand()` 함수를 사용하여 시드를 설정할 수 있습니다. 일반적으로 현재 시간을 기반으로 시드를 설정합니다:

```c
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(0)); // 현재 시간을 시드로 사용
    int random_number = rand();
    printf("Generated Random Number: %d\n", random_number);
    return 0;
}
```

- **범위 조정**: `rand()`의 반환 값을 특정 범위로 조정하려면 다음과 같이 사용할 수 있습니다:

```c
int lower_bound = 1;
int upper_bound = 100;
int random_number = (rand() % (upper_bound - lower_bound + 1)) + lower_bound;
```

## 예제
다음은 `rand()` 함수의 기본 사용 예시입니다.

1. 기본 난수 생성
```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    srand(0); // 고정된 시드 사용
    printf("%d\n", rand());
    printf("%d\n", rand());
    return 0;
}
```

2. 범위 내 난수 생성
```c
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

int main() {
    srand(time(0)); // 현재 시간을 시드로 사용
    for (int i = 0; i < 5; i++) {
        int random_number = (rand() % 10) + 1; // 1부터 10까지의 난수
        printf("%d\n", random_number);
    }
    return 0;
}
```

## 설명
`rand()` 함수를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **시드 문제**: 동일한 시드 값을 사용하면 매번 같은 난수를 생성하게 됩니다. 따라서 다양한 난수를 생성하려면 `srand()`로 시드를 설정해야 합니다.
- **균등 분포**: `rand()`는 균등 분포의 의사 난수를 생성하지만, 특정 상황에서는 패턴이 나타날 수 있습니다. 따라서 고급 난수 생성이 필요할 경우 다른 라이브러리나 알고리즘을 고려해야 합니다.
- **스레드 안전성**: `rand()` 함수는 기본적으로 스레드 안전하지 않으므로 멀티스레딩 환경에서는 주의가 필요합니다.

## 한 줄 요약
C 언어의 `rand()` 함수는 의사 난수를 생성하는 기본 함수로, 다양한 응용 프로그램에서 무작위 수를 생성하는 데 사용됩니다.