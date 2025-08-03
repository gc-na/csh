<!--
Meta Description: # bsearch: Die binäre Suche in C für effiziente Datenfindung ## Synopsis Die Funktion `bsearch` in C ermöglicht die schnelle Suche nach einem Element ...
Meta Keywords: die, bsearch, int, void, const
-->

# bsearch: Die binäre Suche in C für effiziente Datenfindung

## Synopsis
Die Funktion `bsearch` in C ermöglicht die schnelle Suche nach einem Element in einem sortierten Array mithilfe des binären Suchalgorithmus.

## Dokumentation
### Zweck
`bsearch` ist eine Funktion, die in der Standardbibliothek von C definiert ist und zur Durchführung einer binären Suche verwendet wird. Diese Funktion ermöglicht es, ein bestimmtes Element in einem sortierten Array zu finden, was deutlich schneller ist als eine lineare Suche, insbesondere bei großen Datenmengen.

### Verwendung
Die Funktion hat die folgende Signatur:

```c
void *bsearch(const void *key, const void *base, size_t nmemb, size_t size, 
              int (*compar)(const void *, const void *));
```

#### Parameter:
- `key`: Ein Zeiger auf das Element, das gesucht wird.
- `base`: Ein Zeiger auf das erste Element des sortierten Arrays.
- `nmemb`: Die Anzahl der Elemente im Array.
- `size`: Die Größe eines einzelnen Elements im Array.
- `compar`: Ein Zeiger auf eine Vergleichsfunktion, die zwei Elemente vergleicht und einen negativen Wert, null oder einen positiven Wert zurückgibt, abhängig davon, ob das erste Element kleiner, gleich oder größer als das zweite ist.

#### Rückgabewert:
`bsearch` gibt einen Zeiger auf das gefundene Element zurück, oder `NULL`, wenn das Element nicht gefunden wurde.

### Details
Die `bsearch`-Funktion erwartet, dass das Array, in dem gesucht wird, bereits sortiert ist. Der Vergleichsoperator muss korrekt implementiert sein, da eine falsche Implementierung zu unerwarteten Ergebnissen führen kann. Die Vergleichsfunktion sollte wie folgt definiert sein:

```c
int compar(const void *a, const void *b);
```

## Beispiele
### Beispiel 1: Einfache Verwendung von `bsearch`
```c
#include <stdio.h>
#include <stdlib.h>

int compar(const void *a, const void *b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int arr[] = {1, 3, 5, 7, 9};
    int key = 5;
    int *p = bsearch(&key, arr, 5, sizeof(int), compar);
    
    if (p != NULL) {
        printf("Element gefunden: %d\n", *p);
    } else {
        printf("Element nicht gefunden.\n");
    }
    return 0;
}
```

### Beispiel 2: Verwendung von `bsearch` mit benutzerdefinierten Strukturen
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
    int id;
    char name[20];
} Person;

int compar(const void *a, const void *b) {
    return ((Person*)a)->id - ((Person*)b)->id;
}

int main() {
    Person people[] = {{1, "Alice"}, {2, "Bob"}, {3, "Charlie"}};
    Person key = {2, ""}; // Nur ID wird verwendet
    Person *p = bsearch(&key, people, 3, sizeof(Person), compar);
    
    if (p != NULL) {
        printf("Person gefunden: %s\n", p->name);
    } else {
        printf("Person nicht gefunden.\n");
    }
    return 0;
}
```

## Erklärung
Ein häufiges Problem bei der Verwendung von `bsearch` ist die Unsicherheit über die Sortierung des Arrays. Wenn das Array nicht sortiert ist, kann die Funktion falsche Ergebnisse liefern. Außerdem sollte die Vergleichsfunktion genau definiert sein, um korrekte Vergleiche zu gewährleisten. Beachten Sie, dass `bsearch` nicht für Arrays geeignet ist, die sich dynamisch ändern, da die Sortierung nach jeder Änderung aufrechterhalten werden muss.

## Ein-Satz-Zusammenfassung
Die `bsearch`-Funktion in C ermöglicht eine effiziente binäre Suche in sortierten Arrays und ist entscheidend für die Optimierung von Suchoperationen.