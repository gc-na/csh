<!--
Meta Description: # malloc in C: Dynamische Speicherzuweisung verstehen ## Synopsis `malloc` ist eine Funktion in der Programmiersprache C, die zur dynamischen Speicher...
Meta Keywords: malloc, speicher, die, ist, der
-->

# malloc in C: Dynamische Speicherzuweisung verstehen

## Synopsis
`malloc` ist eine Funktion in der Programmiersprache C, die zur dynamischen Speicherzuweisung verwendet wird. Sie ermöglicht es, zur Laufzeit Speicherplatz für Datenstrukturen zu reservieren, was besonders nützlich ist, wenn die Größe der benötigten Daten zur Kompilierungszeit nicht bekannt ist.

## Dokumentation
Die Funktion `malloc` (kurz für "memory allocation") ist Bestandteil der Standardbibliothek von C und wird über die Header-Datei `<stdlib.h>` bereitgestellt. Ihr Hauptzweck besteht darin, einen Block von Speicher in Bytes zu reservieren und einen Zeiger auf den Anfang dieses Speicherblocks zurückzugeben.

### Syntax
```c
#include <stdlib.h>

void* malloc(size_t size);
```

### Parameter
- **size**: Die Anzahl der Bytes, die zugewiesen werden sollen.

### Rückgabewert
- `malloc` gibt einen Zeiger auf den zugewiesenen Speicherblock zurück. Wenn die Zuweisung fehlschlägt (z.B. wenn nicht genügend Speicher verfügbar ist), wird `NULL` zurückgegeben.

### Verwendung
Um `malloc` effektiv zu nutzen, sollte der zurückgegebene Zeiger immer auf `NULL` überprüft werden, um sicherzustellen, dass die Speicherzuweisung erfolgreich war.

## Beispiele
### Beispiel 1: Einfache Verwendung von malloc
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *array;
    int n = 5;

    // Speicher für ein Array von 5 Ganzzahlen reservieren
    array = (int*)malloc(n * sizeof(int));

    if (array == NULL) {
        printf("Speicherzuweisung fehlgeschlagen!\n");
        return 1;
    }

    // Beispiel: Array initialisieren
    for (int i = 0; i < n; i++) {
        array[i] = i * 10;
        printf("%d ", array[i]);
    }

    // Speicher freigeben
    free(array);
    return 0;
}
```

### Beispiel 2: Verwendung mit komplexen Datenstrukturen
```c
#include <stdio.h>
#include <stdlib.h>

typedef struct {
    int id;
    char name[50];
} Person;

int main() {
    Person *p;

    // Speicher für eine Person reservieren
    p = (Person*)malloc(sizeof(Person));

    if (p == NULL) {
        printf("Speicherzuweisung fehlgeschlagen!\n");
        return 1;
    }

    // Werte zuweisen
    p->id = 1;
    snprintf(p->name, sizeof(p->name), "Max Mustermann");

    printf("ID: %d, Name: %s\n", p->id, p->name);

    // Speicher freigeben
    free(p);
    return 0;
}
```

## Erklärung
Bei der Verwendung von `malloc` gibt es einige häufige Fallstricke:

- **Speicherlecks**: Wenn der zugewiesene Speicher nicht mit `free` freigegeben wird, bleibt der Speicher belegt, was zu einem Speicherleck führt. Es ist wichtig, sicherzustellen, dass jeder mit `malloc` zugewiesene Speicher auch wieder freigegeben wird.
  
- **NULL-Überprüfung**: Es ist entscheidend, den Rückgabewert von `malloc` auf `NULL` zu überprüfen, um sicherzustellen, dass der Speicher erfolgreich zugewiesen wurde. Ein Zugriff auf einen `NULL`-Zeiger führt zu einem Programmabsturz.

- **Typumwandlung**: In C ist eine Typumwandlung beim Zuweisen von Zeigern nicht zwingend erforderlich, da die Rückgabe von `malloc` als `void*` erfolgt. Dennoch kann es in C++ erforderlich sein, den Zeiger zu casten.

## Einzeilensummary
`malloc` ist eine Funktion in C zur dynamischen Speicherzuweisung, die zur Laufzeit benötigten Speicher bereitstellt.