<!--
Meta Description: # C 언어의 toupper 함수: 대문자로 변환하기 ## 개요 C 언어에서 `toupper` 함수는 주어진 문자(c)를 대문자로 변환하여 반환하는 함수입니다. 이 함수는 문자 처리 및 문자열 조작에 유용하게 사용됩니다. ## 문서화 ### 목적 `toupper` 함수...
Meta Keywords: toupper, 함수는, int, 대문자로, include
-->

# C 언어의 toupper 함수: 대문자로 변환하기

## 개요
C 언어에서 `toupper` 함수는 주어진 문자(c)를 대문자로 변환하여 반환하는 함수입니다. 이 함수는 문자 처리 및 문자열 조작에 유용하게 사용됩니다.

## 문서화

### 목적
`toupper` 함수는 특정 문자가 소문자인 경우 해당 문자를 대문자로 변환하여 반환합니다. 만약 입력된 문자가 이미 대문자이거나 대문자로 변환할 수 없는 문자라면, 입력된 문자를 그대로 반환합니다.

### 사용법
`toupper` 함수는 `<ctype.h>` 헤더 파일에 정의되어 있습니다. 기본적인 사용법은 다음과 같습니다:

```c
#include <ctype.h>

int toupper(int c);
```

#### 매개변수
- `c`: 변환할 문자로, `int` 형식의 ASCII 값을 입력받습니다.

#### 반환값
- 변환된 대문자(또는 입력된 문자)를 반환합니다. 반환값은 `int` 형식입니다.

## 예제
다음은 `toupper` 함수의 기본 사용 예제입니다.

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char lower = 'a';
    char upper = toupper(lower);
    
    printf("소문자: %c, 대문자: %c\n", lower, upper);
    
    return 0;
}
```

이 코드는 'a'를 대문자 'A'로 변환하여 출력합니다.

### 여러 문자의 변환 예제
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[] = "hello world!";
    
    for(int i = 0; str[i] != '\0'; i++) {
        str[i] = toupper(str[i]);
    }
    
    printf("대문자 변환: %s\n", str);
    
    return 0;
}
```

이 코드는 문자열 "hello world!"를 "HELLO WORLD!"로 변환합니다.

## 설명
`toupper` 함수를 사용할 때 주의할 점은 다음과 같습니다:

- 함수는 ASCII 문자 집합을 기준으로 작동하므로, 비ASCII 문자의 경우 기대한 대로 작동하지 않을 수 있습니다.
- `toupper`는 정수형 매개변수를 받지만, 문자형 변수를 전달할 때는 문자의 ASCII 값을 정수형으로 자동 변환하여 처리합니다.
- `toupper` 함수는 소문자 외에도 공백 문자, 숫자 등 대문자로 변환할 수 없는 문자를 그대로 반환합니다.

## 한 줄 요약
C 언어의 `toupper` 함수는 소문자를 대문자로 변환하는 유용한 문자 처리 함수입니다.