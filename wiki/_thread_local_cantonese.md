<!--
Meta Description: # C 語言中的 _Thread_local：多線程變數的管理 ## Synopsis `_Thread_local` 是 C 語言中用於指定變數為線程本地存儲的關鍵字，這意味著每個線程都擁有自己的變數副本。 ## Documentation 在多線程編程中，`_Thread_local` 關鍵字用...
Meta Keywords: _thread_local, null, int, thread_local_counter, void
-->

# C 語言中的 _Thread_local：多線程變數的管理

## Synopsis
`_Thread_local` 是 C 語言中用於指定變數為線程本地存儲的關鍵字，這意味著每個線程都擁有自己的變數副本。

## Documentation
在多線程編程中，`_Thread_local` 關鍵字用來定義線程本地存儲變數。這些變數對每個運行的線程都是獨立的，能夠避免多個線程之間的數據競爭問題。使用 `_Thread_local` 可以讓開發者在多線程環境下更安全地存取和修改變數，因為每個線程都運行在自己的變數上下文中。

### 定義
要定義一個線程本地變數，您只需在變數聲明中加入 `_Thread_local` 關鍵字，如下所示：

```c
_Thread_local int thread_local_var = 0;
```

### 使用
`_Thread_local` 變數可以在函數、全局範圍內定義，並且可以用於存儲任何資料類型。當一個線程修改該變數時，其他線程無法看到這些修改，這樣就避免了數據不一致的問題。

## Examples
以下是 `_Thread_local` 的基本使用範例：

```c
#include <stdio.h>
#include <pthread.h>

_Thread_local int thread_local_counter = 0;

void* thread_function(void* arg) {
    for (int i = 0; i < 5; i++) {
        thread_local_counter++;
        printf("Thread %ld: counter = %d\n", (long)arg, thread_local_counter);
    }
    return NULL;
}

int main() {
    pthread_t thread1, thread2;

    pthread_create(&thread1, NULL, thread_function, (void*)1);
    pthread_create(&thread2, NULL, thread_function, (void*)2);

    pthread_join(thread1, NULL);
    pthread_join(thread2, NULL);

    return 0;
}
```

在這個範例中，`thread_local_counter` 是一個線程本地變數，每個線程都有自己獨立的計數器。

## Explanation
使用 `_Thread_local` 時需要注意以下幾點：

1. **初始化**：線程本地變數在每個線程開始時會被初始化為其指定的初始值。
2. **性能考量**：雖然 `_Thread_local` 提供了方便的線程隔離，但在某些情況下，過度使用可能會影響性能，特別是在高頻訪問的情況下。
3. **跨平台使用**：`_Thread_local` 是 C11 標準的一部分，因此在不支持 C11 的編譯器上可能無法使用。

## One Line Summary
`_Thread_local` 關鍵字在 C 語言中用於定義每個線程擁有獨立副本的變數，從而避免多線程間的數據競爭問題。