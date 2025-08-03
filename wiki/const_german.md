<!--
Meta Description: # Der Einsatz von "const" in C: Eine umfassende Anleitung ## Synopsis In der Programmiersprache C dient das Schlüsselwort "const" dazu, Variablen als ...
Meta Keywords: der, const, werden, kann, wert
-->

# Der Einsatz von "const" in C: Eine umfassende Anleitung

## Synopsis
In der Programmiersprache C dient das Schlüsselwort "const" dazu, Variablen als konstant zu deklarieren, was bedeutet, dass ihr Wert nach der Initialisierung nicht mehr verändert werden kann. Dies erhöht die Sicherheit und Lesbarkeit des Codes und hilft, unbeabsichtigte Änderungen zu vermeiden.

## Dokumentation
Das Schlüsselwort "const" wird verwendet, um eine Variable als konstant zu deklarieren. Wenn eine Variable als "const" deklariert wird, kann ihr Wert nach der Zuweisung nicht mehr verändert werden. Dies ist besonders nützlich bei der Arbeit mit Funktionen, bei denen Parameter als konstant übergeben werden sollen, um sicherzustellen, dass sie nicht modifiziert werden.

### Verwendung
Die allgemeine Syntax zur Deklaration einer konstanten Variable lautet:

```c
const Datentyp Variablenname = Wert;
```

Beispiel:
```c
const int maxWert = 100;
```

Hier ist `maxWert` eine konstante Ganzzahl, die nicht mehr verändert werden kann.

### Details
- **Konstanz bei Zeigern**: Das Schlüsselwort "const" kann auch in Verbindung mit Zeigern verwendet werden. Dies kann auf zwei Arten geschehen:
  - Ein Zeiger auf eine konstante Variable:
    ```c
    const int *ptr;
    ```
    Hier kann der Zeiger `ptr` auf verschiedene ganzzahlige Werte zeigen, aber der Wert, auf den er zeigt, kann nicht verändert werden.
  
  - Ein konstanter Zeiger auf eine Variable:
    ```c
    int *const ptr;
    ```
    In diesem Fall kann der Wert, auf den `ptr` zeigt, verändert werden, aber der Zeiger selbst kann nicht auf eine andere Adresse umgeleitet werden.

- **Konstante Arrays**: Ein Array kann ebenfalls als konstant deklariert werden, was bedeutet, dass die Elemente nicht verändert werden können.

## Beispiele
### Beispiel 1: Konstante Variable
```c
#include <stdio.h>

int main() {
    const int maxWert = 10;
    // maxWert = 20; // Fehler: Zuweisung an eine Konstante
    printf("Der maximale Wert ist: %d\n", maxWert);
    return 0;
}
```

### Beispiel 2: Konstanter Zeiger
```c
#include <stdio.h>

void druckeWert(const int *wert) {
    printf("Der Wert ist: %d\n", *wert);
}

int main() {
    int zahl = 5;
    druckeWert(&zahl); // Übergabe der Adresse von zahl
    return 0;
}
```

## Erklärung
Ein häufiger Fehler ist, dass Programmierer versuchen, den Wert einer konstanten Variablen nach der Initialisierung zu ändern, was zu Kompilierungsfehlern führt. Ein weiteres Missverständnis kann die Verwendung von "const" mit Zeigern sein. Es ist wichtig, den Unterschied zwischen einem konstanten Zeiger und einem Zeiger auf eine Konstante zu verstehen, da sie unterschiedliche Verhaltensweisen aufweisen.

Zusätzlich kann "const" in der Definition von Funktionen verwendet werden, um zu verdeutlichen, dass bestimmte Parameter nicht verändert werden sollten. Dies verbessert die Lesbarkeit und Wartbarkeit des Codes.

## Zusammenfassung in einer Zeile
Das Schlüsselwort "const" in C ermöglicht die Deklaration von konstanten Variablen, die nach der Initialisierung nicht mehr verändert werden können, und fördert so die Sicherheit und Lesbarkeit des Codes.