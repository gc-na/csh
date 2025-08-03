<!--
Meta Description: # memcmp: Vergleich von Speicherdaten in C ## Synopsis Die Funktion `memcmp` in C wird verwendet, um zwei Speicherbereiche Byte für Byte zu vergleiche...
Meta Keywords: ist, die, der, memcmp, arr1
-->

# memcmp: Vergleich von Speicherdaten in C

## Synopsis
Die Funktion `memcmp` in C wird verwendet, um zwei Speicherbereiche Byte für Byte zu vergleichen. Sie ist nützlich, um festzustellen, ob zwei Arrays oder Speicherblöcke identisch sind.

## Dokumentation
### Zweck
`memcmp` vergleicht die ersten `n` Bytes von zwei Speicherbereichen. Sie gibt einen ganzzahligen Wert zurück, der den Vergleichsergebnis reflektiert: 
- Ein negativer Wert, wenn der erste Speicherbereich kleiner ist als der zweite,
- Null, wenn beide Speicherbereiche identisch sind,
- Ein positiver Wert, wenn der erste Speicherbereich größer ist.

### Verwendung
Die Syntax der Funktion lautet:

```c
int memcmp(const void *ptr1, const void *ptr2, size_t n);
```

#### Parameter
- `ptr1`: Ein Zeiger auf den ersten Speicherbereich.
- `ptr2`: Ein Zeiger auf den zweiten Speicherbereich.
- `n`: Die Anzahl der zu vergleichenden Bytes.

#### Rückgabewert
`memcmp` gibt einen ganzzahligen Wert zurück:
- < 0: `ptr1` ist kleiner als `ptr2`
- = 0: `ptr1` ist gleich `ptr2`
- > 0: `ptr1` ist größer als `ptr2`

### Details
Die Funktion ist Teil der Standardbibliothek `<string.h>`. Sie eignet sich für den Vergleich von binären Daten, wie etwa Arrays oder Strukturen. 

## Beispiele
### Beispiel 1: Vergleich von zwei Arrays
```c
#include <stdio.h>
#include <string.h>

int main() {
    char arr1[] = "Hello";
    char arr2[] = "Hello";
    
    int result = memcmp(arr1, arr2, sizeof(arr1));
    
    if (result == 0) {
        printf("Arrays sind identisch.\n");
    } else {
        printf("Arrays sind unterschiedlich.\n");
    }
    
    return 0;
}
```

### Beispiel 2: Vergleich von unterschiedlichen Arrays
```c
#include <stdio.h>
#include <string.h>

int main() {
    char arr1[] = "Hello";
    char arr2[] = "World";
    
    int result = memcmp(arr1, arr2, sizeof(arr1));
    
    if (result < 0) {
        printf("arr1 ist kleiner als arr2.\n");
    } else {
        printf("arr1 ist größer als arr2.\n");
    }
    
    return 0;
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `memcmp` ist das falsche Festlegen der Anzahl der zu vergleichenden Bytes. Wenn `n` größer ist als die tatsächliche Größe eines der Speicherbereiche, kann dies zu undefiniertem Verhalten führen. Zudem kann `memcmp` nicht die Gleichheit von NULL-Zeigern überprüfen, also muss sichergestellt werden, dass die Zeiger gültig sind. 

Ein weiterer Punkt ist, dass `memcmp` nur die Bytes vergleicht und keine Typen berücksichtigt. Dies bedeutet, dass die Art der Daten in den Speicherbereichen irrelevant ist; es wird einfach Byte für Byte verglichen.

## Ein-Satz-Zusammenfassung
Die Funktion `memcmp` in C vergleicht zwei Speicherbereiche und gibt zurück, ob sie identisch sind oder nicht, indem sie die ersten `n` Bytes vergleicht.