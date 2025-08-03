<!--
Meta Description: # memcpy in C: Eine umfassende Anleitung zur Speicherkopierung ## Synopsis Die Funktion `memcpy` ist eine Standardbibliotheksfunktion in C, die verwen...
Meta Keywords: die, memcpy, ist, von, werden
-->

# memcpy in C: Eine umfassende Anleitung zur Speicherkopierung

## Synopsis
Die Funktion `memcpy` ist eine Standardbibliotheksfunktion in C, die verwendet wird, um Daten von einem Speicherort in einen anderen zu kopieren. Sie ist besonders nützlich für die Bearbeitung von Arrays und strukturierten Datentypen.

## Dokumentation
Die Funktion `memcpy` ist Teil der C-Standardbibliothek und wird im Header `<string.h>` deklariert. Die allgemeine Syntax lautet:

```c
void *memcpy(void *dest, const void *src, size_t n);
```

### Parameter
- **dest**: Ein Zeiger auf den Zielspeicherort, in den die Daten kopiert werden.
- **src**: Ein Zeiger auf den Quellspeicherort, von dem die Daten kopiert werden.
- **n**: Die Anzahl der Bytes, die kopiert werden sollen.

### Rückgabewert
Die Funktion gibt einen Zeiger auf den Zielspeicherort (`dest`) zurück.

### Zweck
`memcpy` wird verwendet, um eine bestimmte Anzahl von Bytes von einem Speicherort zu einem anderen zu kopieren. Diese Funktion ist effizient und wird häufig in Situationen eingesetzt, in denen große Datenmengen verarbeitet werden müssen.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `memcpy`:

### Beispiel 1: Kopieren eines Arrays
```c
#include <stdio.h>
#include <string.h>

int main() {
    char source[] = "Hallo, Welt!";
    char destination[20];

    memcpy(destination, source, strlen(source) + 1); // +1 für das Nullterminator
    printf("Kopierter Text: %s\n", destination);

    return 0;
}
```

### Beispiel 2: Kopieren von Strukturen
```c
#include <stdio.h>
#include <string.h>

typedef struct {
    int id;
    char name[20];
} Person;

int main() {
    Person p1 = {1, "Max Mustermann"};
    Person p2;

    memcpy(&p2, &p1, sizeof(Person));
    printf("ID: %d, Name: %s\n", p2.id, p2.name);

    return 0;
}
```

## Erklärung
Obwohl `memcpy` eine sehr nützliche Funktion ist, gibt es einige häufige Stolpersteine, die bei der Nutzung beachtet werden sollten:

1. **Überlappende Speicherbereiche**: `memcpy` ist nicht sicher, wenn sich die Quell- und Zielbereiche überlappen. In solchen Fällen sollte `memmove` verwendet werden, das sicherstellt, dass die Daten korrekt kopiert werden.
   
2. **Größe des Ziels**: Es ist wichtig sicherzustellen, dass der Zielpuffer groß genug ist, um die zu kopierenden Daten zu speichern. Andernfalls kann es zu Speicherbeschädigungen kommen, die zu undefiniertem Verhalten führen.

3. **Null-Terminator**: Bei der Kopie von Strings sollte darauf geachtet werden, dass der Nullterminator (für C-Strings) ebenfalls kopiert wird, um sicherzustellen, dass der kopierte String korrekt endet.

## Ein-Satz-Zusammenfassung
`memcpy` ist eine leistungsstarke Funktion in C zur effizienten Kopie von Speicherinhalten zwischen verschiedenen Speicheradressen.