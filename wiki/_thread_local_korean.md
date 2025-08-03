<!--
Meta Description: # C 언어에서의 _Thread_local: 쓰레드 로컬 저장소 ## 개요 `_Thread_local`은 C 언어에서 사용되는 키워드로, 멀티쓰레드 환경에서 각 쓰레드가 독립적으로 사용하는 변수를 정의하는 데 사용된다. 이는 데이터의 공유를 방지하고 각 쓰레드가 고유한...
Meta Keywords: _thread_local, 쓰레드가, 변수를, thread, thread_local_var
-->

# C 언어에서의 _Thread_local: 쓰레드 로컬 저장소

## 개요
`_Thread_local`은 C 언어에서 사용되는 키워드로, 멀티쓰레드 환경에서 각 쓰레드가 독립적으로 사용하는 변수를 정의하는 데 사용된다. 이는 데이터의 공유를 방지하고 각 쓰레드가 고유한 값을 가질 수 있도록 도와준다.

## 문서화
### 목적
`_Thread_local`은 여러 쓰레드가 실행되는 프로그램에서 데이터의 안전한 사용을 보장하기 위해 도입된 기능이다. 이를 통해 각 쓰레드는 자신의 데이터를 유지할 수 있으며, 다른 쓰레드의 데이터와 충돌을 피할 수 있다.

### 사용법
`_Thread_local` 키워드는 변수를 선언할 때 사용된다. 이를 통해 해당 변수가 쓰레드 로컬 저장소에 저장되어, 각 쓰레드가 이 변수의 독립적인 복사본을 가지도록 한다.

```c
#include <stdio.h>
#include <pthread.h>

void* thread_function(void* arg) {
    _Thread_local int thread_local_var = 0;
    thread_local_var++;
    printf("Thread %ld: %d\n", (long)arg, thread_local_var);
    return NULL;
}

int main() {
    pthread_t threads[5];
    for (long i = 0; i < 5; i++) {
        pthread_create(&threads[i], NULL, thread_function, (void*)i);
    }
    for (int i = 0; i < 5; i++) {
        pthread_join(threads[i], NULL);
    }
    return 0;
}
```

## 예제
위의 코드는 5개의 쓰레드를 생성하고 각 쓰레드에서 `_Thread_local` 변수를 증가시키는 예제이다. 각 쓰레드는 자신의 `thread_local_var` 값을 독립적으로 증가시키며, 출력 결과는 다음과 같다:

```
Thread 0: 1
Thread 1: 1
Thread 2: 1
Thread 3: 1
Thread 4: 1
```

## 설명
### 일반적인 함정 및 주의사항
- `_Thread_local` 변수를 선언할 때 초기값을 지정하지 않으면 해당 변수는 자동으로 0으로 초기화된다.
- 이 기능은 C11 표준에서 도입되었으므로, 이를 지원하는 컴파일러에서만 사용할 수 있다. 구버전의 컴파일러에서는 호환성 문제가 발생할 수 있다.
- `_Thread_local` 변수를 전역 변수로 선언하면, 모든 쓰레드가 자신의 복사본을 가지게 되지만, 함수 내부에서 선언된 경우 해당 함수가 호출될 때마다 새로운 복사본이 생성된다.
- `static` 키워드와 함께 사용하는 것이 일반적이며, 이를 통해 변수가 함수의 호출 간에도 유지되도록 할 수 있다.

## 한 줄 요약
`_Thread_local`은 C 언어에서 멀티쓰레드 환경에서 각 쓰레드가 독립적인 변수를 가질 수 있도록 돕는 키워드이다.