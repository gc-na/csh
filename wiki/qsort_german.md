<!--
Meta Description: # qsort in C: Eine umfassende Anleitung zur Sortierfunktion ## Synopsis `qsort` ist eine in der C-Standardbibliothek definierte Funktion, die einen Ar...
Meta Keywords: die, const, qsort, void, int
-->

# qsort in C: Eine umfassende Anleitung zur Sortierfunktion

## Synopsis
`qsort` ist eine in der C-Standardbibliothek definierte Funktion, die einen Array von Elementen in aufsteigender Reihenfolge sortiert. Sie nutzt den Quicksort-Algorithmus, um eine effiziente Sortierung zu gewährleisten.

## Documentation
### Zweck
Die Funktion `qsort` wird verwendet, um eine Liste von Elementen in C zu sortieren. Sie ist Teil der `<stdlib.h>`-Bibliothek und ermöglicht eine flexible Sortierung von Arrays beliebiger Datentypen, sofern der Benutzer einen Vergleichs-Callback bereitstellt.

### Nutzung
Die Funktion hat die folgende Syntax:

```c
void qsort(void *base, size_t num, size_t size, int (*compar)(const void *, const void *));
```

#### Parameter
- `base`: Ein Zeiger auf das erste Element des Arrays, das sortiert werden soll.
- `num`: Die Anzahl der Elemente im Array.
- `size`: Die Größe eines einzelnen Elements im Array (in Bytes).
- `compar`: Ein Zeiger auf eine Vergleichsfunktion, die zwei Elemente vergleicht und eine Ganzzahl zurückgibt.

#### Vergleichsfunktion
Die Vergleichsfunktion muss die folgende Signatur haben:

```c
int compar(const void *a, const void *b);
```

Sie gibt einen Wert kleiner als 0 zurück, wenn `a` vor `b` kommen soll, 0, wenn sie gleich sind, und einen Wert größer als 0, wenn `a` nach `b` kommen soll.

## Beispiele
Hier sind einige einfache Beispiele, um die Verwendung von `qsort` zu demonstrieren.

### Beispiel 1: Sortieren eines Arrays von Ganzzahlen
```c
#include <stdio.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return (*(int *)a - *(int *)b);
}

int main() {
    int arr[] = {5, 2, 8, 1, 3};
    size_t arr_size = sizeof(arr) / sizeof(arr[0]);

    qsort(arr, arr_size, sizeof(int), compare);

    for (size_t i = 0; i < arr_size; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
```

### Beispiel 2: Sortieren eines Arrays von Zeichenfolgen
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int compareStrings(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

int main() {
    const char *arr[] = {"Banane", "Apfel", "Kiwi", "Orange"};
    size_t arr_size = sizeof(arr) / sizeof(arr[0]);

    qsort(arr, arr_size, sizeof(const char *), compareStrings);

    for (size_t i = 0; i < arr_size; i++) {
        printf("%s ", arr[i]);
    }
    return 0;
}
```

## Erklärung
### Häufige Fallstricke
- **Vergleichsfunktion**: Stellen Sie sicher, dass Ihre Vergleichsfunktion korrekt implementiert ist. Ein fehlerhaftes Verhalten kann zu unerwarteten Ergebnissen führen.
- **Datentypen**: Achten Sie darauf, dass die Größe (`size`) und der Typ des Arrays korrekt angegeben werden, um Speicherfehler zu vermeiden.
- **Null-Zeiger**: Überprüfen Sie, ob der `base`-Zeiger und die Anzahl der Elemente (`num`) nicht null sind, um Segmentation Faults zu vermeiden.

### Zusätzliche Hinweise
- Die `qsort`-Funktion ist nicht stabil, was bedeutet, dass die Reihenfolge von gleichwertigen Elementen nicht garantiert wird.
- Die Leistung von `qsort` kann je nach Verteilung der Daten variieren. In den meisten Fällen ist es jedoch sehr effizient.

## One Line Summary
`qsort` ist eine leistungsstarke und flexible Funktion in C, die Arrays effizient sortiert, indem sie eine benutzerdefinierte Vergleichsfunktion verwendet.