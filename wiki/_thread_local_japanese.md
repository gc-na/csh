<!--
Meta Description: # C言語における_thread_localの使い方と重要性 ## 概要 `_Thread_local` は、C言語においてスレッドローカルストレージを実現するためのキーワードです。この機能を使用することで、各スレッドが独自の変数インスタンスを持つことができ、スレッド間のデータ競合を防ぐことができま...
Meta Keywords: int, _thread_local, null, threads, void
-->

# C言語における_thread_localの使い方と重要性

## 概要
`_Thread_local` は、C言語においてスレッドローカルストレージを実現するためのキーワードです。この機能を使用することで、各スレッドが独自の変数インスタンスを持つことができ、スレッド間のデータ競合を防ぐことができます。

## ドキュメント
### 目的
`_Thread_local` は、マルチスレッドプログラミングにおいて、スレッドごとに異なるデータを保持するための仕組みです。このキーワードを使用することで、スレッドが同じ変数名を持つ場合でも、各スレッドが独自の値を持つことができます。

### 使用法
`_Thread_local` キーワードは、変数宣言の前に配置します。これにより、その変数はスレッドローカル変数として扱われます。たとえば、以下のように定義します。

```c
#include <stdio.h>
#include <pthread.h>

_Thread_local int thread_local_var = 0;

void* thread_function(void* arg) {
    thread_local_var++;
    printf("Thread %d: %d\n", *(int*)arg, thread_local_var);
    return NULL;
}

int main() {
    pthread_t threads[2];
    int thread_ids[2] = {1, 2};

    for (int i = 0; i < 2; i++) {
        pthread_create(&threads[i], NULL, thread_function, &thread_ids[i]);
    }

    for (int i = 0; i < 2; i++) {
        pthread_join(threads[i], NULL);
    }

    return 0;
}
```

### 詳細
- `_Thread_local` はC11以降でサポートされており、スレッドごとに異なるストレージを確保します。
- スレッドローカル変数は初期化され、スレッドのライフサイクルが終了するまで保持されます。
- スレッドが変数にアクセスすると、他のスレッドがその変数を変更した場合でも、スレッドは自分自身の値を持ち続けます。

## 例
以下は、スレッドローカル変数を使用した簡単な例です。本プログラムでは、各スレッドが独自のカウンタを持ち、それをインクリメントして表示します。

```c
#include <stdio.h>
#include <pthread.h>

_Thread_local int counter = 0;

void* increment_counter(void* arg) {
    for (int i = 0; i < 5; i++) {
        counter++;
    }
    printf("Counter in thread %ld: %d\n", (long)arg, counter);
    return NULL;
}

int main() {
    pthread_t threads[3];

    for (long i = 0; i < 3; i++) {
        pthread_create(&threads[i], NULL, increment_counter, (void*)i);
    }

    for (int i = 0; i < 3; i++) {
        pthread_join(threads[i], NULL);
    }

    return 0;
}
```

## 説明
- `_Thread_local` 変数は、スレッド間で共有されないため、データ競合を避けることができますが、全てのコンパイラがこの機能をサポートしているわけではありません。使用する前に、コンパイラのドキュメントを確認してください。
- スレッドローカル変数は、グローバルまたは静的な変数としてのみ使用できますので、ローカル関数内での使用はできません。

## 一文要約
`_Thread_local` は、C言語におけるマルチスレッドプログラミングで、スレッドごとに独立した変数を持つためのキーワードです。