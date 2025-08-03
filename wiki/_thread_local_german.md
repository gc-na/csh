<!--
Meta Description: # _Thread_local in C: Eine umfassende Anleitung zur Verwendung von Thread-spezifischen Variablen ## Synopsis Das Schlüsselwort `_Thread_local` in C er...
Meta Keywords: thread, variablen, _thread_local, threads, int
-->

# _Thread_local in C: Eine umfassende Anleitung zur Verwendung von Thread-spezifischen Variablen

## Synopsis
Das Schlüsselwort `_Thread_local` in C ermöglicht die Deklaration von Variablen, die für jeden Thread in einem Multithread-Programm lokal sind. Dies bedeutet, dass jeder Thread seine eigene Instanz der Variablen hat, wodurch Datenkonflikte vermieden werden.

## Documentation
### Zweck
Das `_Thread_local` Schlüsselwort wurde mit C11 eingeführt und ermöglicht die Definition von Variablen, die in jedem Thread unabhängig sind. Dies ist besonders wichtig in Multithread-Umgebungen, wo Threads gleichzeitig auf gemeinsame Daten zugreifen können. Mit der Thread-lokalen Speicherung wird sichergestellt, dass jeder Thread seine eigene Kopie der Variablen hat.

### Verwendung
Die Syntax zur Deklaration einer Thread-lokalen Variablen lautet:

```c
_Thread_local Datentyp Variablenname;
```

Bei der Verwendung von `_Thread_local` ist zu beachten, dass diese Variablen statisch initialisiert werden. Das bedeutet, dass sie ihren Wert zwischen den Funktionsaufrufen beibehalten, jedoch nicht mit anderen Threads geteilt werden.

#### Beispiel:
```c
#include <stdio.h>
#include <pthread.h>

_Thread_local int thread_local_var = 0;

void* thread_function(void* arg) {
    thread_local_var++;
    printf("Thread %d: thread_local_var = %d\n", (int)(size_t)arg, thread_local_var);
    return NULL;
}

int main() {
    pthread_t threads[3];
    for (int i = 0; i < 3; i++) {
        pthread_create(&threads[i], NULL, thread_function, (void*)(size_t)i);
    }
    for (int i = 0; i < 3; i++) {
        pthread_join(threads[i], NULL);
    }
    return 0;
}
```

### Details
- **Initialisierung:** Thread-lokale Variablen werden beim ersten Zugriff durch den jeweiligen Thread initialisiert.
- **Lebensdauer:** Die Lebensdauer der `_Thread_local` Variablen entspricht der Lebensdauer des Threads. Sie werden zerstört, wenn der Thread endet.
- **Speicherort:** Diese Variablen werden im statischen Speicherbereich des Programms abgelegt, sind jedoch nicht für andere Threads zugänglich.

## Examples
1. **Einfache Verwendung:**

```c
#include <stdio.h>

_Thread_local int count = 0;

void increment() {
    count++;
    printf("Count: %d\n", count);
}
```

2. **Multithread-Beispiel:**

```c
#include <stdio.h>
#include <pthread.h>

_Thread_local int thread_id;

void* print_thread_id(void* arg) {
    thread_id = (int)(size_t)arg;
    printf("Thread ID: %d\n", thread_id);
    return NULL;
}

int main() {
    pthread_t threads[5];
    for (int i = 0; i < 5; i++) {
        pthread_create(&threads[i], NULL, print_thread_id, (void*)(size_t)i);
    }
    for (int i = 0; i < 5; i++) {
        pthread_join(threads[i], NULL);
    }
    return 0;
}
```

## Explanation
### Häufige Fallstricke
- **Nicht unterstützte Compiler:** Ältere Compiler unterstützen möglicherweise nicht das `_Thread_local` Schlüsselwort. Stellen Sie sicher, dass Sie einen C11-kompatiblen Compiler verwenden.
- **Globale Variablen:** `_Thread_local` Variablen sind nicht global. Wenn eine Variable in einem anderen Thread benötigt wird, muss eine Synchronisation implementiert werden.
- **Ressourcenverbrauch:** Thread-lokale Variablen belegen Speicher für jeden Thread. Achten Sie darauf, die Anzahl der Threads und die Anzahl der Thread-lokalen Variablen zu berücksichtigen, um den Speicherverbrauch zu minimieren.

## One Line Summary
Das `_Thread_local` Schlüsselwort in C ermöglicht die sichere Verwendung von Variablen innerhalb von Threads, indem es jeder Thread-Instanz eigene Kopien der Variablen zuweist.