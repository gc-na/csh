<!--
Meta Description: # realloc in C: Dynamische Speicheranpassung leicht gemacht ## Synopsis Die Funktion `realloc` in C ermöglicht die Anpassung der Größe eines zuvor all...
Meta Keywords: realloc, der, arr, die, int
-->

# realloc in C: Dynamische Speicheranpassung leicht gemacht

## Synopsis
Die Funktion `realloc` in C ermöglicht die Anpassung der Größe eines zuvor allokierten Speichers. Sie ist ein essentielles Werkzeug für die dynamische Speicherverwaltung und hilft dabei, den Speicher effizient zu nutzen.

## Dokumentation
Die `realloc`-Funktion wird verwendet, um die Größe eines bereits mit `malloc` oder `calloc` zugewiesenen Blocks von Speicher zu ändern. Sie ist Bestandteil der Standardbibliothek `<stdlib.h>`. 

### Zweck
`realloc` ermöglicht es, die Größe eines Speicherblocks zu vergrößern oder zu verkleinern. Wenn der neue Speicherblock größer ist, können zusätzliche Bytes verwendet werden. Bei einer Verkleinerung wird nur der benötigte Speicher beibehalten.

### Verwendung
Die Syntax von `realloc` lautet wie folgt:

```c
void* realloc(void* ptr, size_t new_size);
```

- `ptr`: Ein Zeiger auf den aktuell zugewiesenen Speicherblock, dessen Größe geändert werden soll. Wenn `ptr` `NULL` ist, verhält sich `realloc` wie `malloc`.
- `new_size`: Die neue Größe in Bytes, die für den Speicherblock angefordert wird.

### Details
- Wenn `realloc` erfolgreich ist, gibt sie einen Zeiger auf den (möglicherweise) neuen Speicherblock zurück. 
- Wenn nicht genügend Speicher verfügbar ist, bleibt der ursprüngliche Speicherblock unverändert, und `realloc` gibt `NULL` zurück.
- Es ist wichtig, den zurückgegebenen Zeiger zu überprüfen, um Speicherlecks zu vermeiden.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `realloc`:

### Beispiel 1: Vergrößerung eines Speicherblocks
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr = malloc(5 * sizeof(int)); // Allokation von Speicher für 5 Integers
    if (arr == NULL) {
        return 1; // Fehler bei der Allokation
    }

    // Füllen des Arrays
    for (int i = 0; i < 5; i++) {
        arr[i] = i + 1;
    }

    // Vergrößern des Arrays auf 10 Integers
    arr = realloc(arr, 10 * sizeof(int));
    if (arr == NULL) {
        return 1; // Fehler bei der Reallokation
    }

    // Füllen der neuen Elemente
    for (int i = 5; i < 10; i++) {
        arr[i] = i + 1;
    }

    // Ausgabe des Arrays
    for (int i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }

    free(arr); // Speicher freigeben
    return 0;
}
```

### Beispiel 2: Verkleinerung eines Speicherblocks
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr = malloc(5 * sizeof(int));
    if (arr == NULL) {
        return 1; // Fehler bei der Allokation
    }

    // Verkleinern des Arrays auf 3 Integers
    arr = realloc(arr, 3 * sizeof(int));
    if (arr == NULL) {
        return 1; // Fehler bei der Reallokation
    }

    free(arr); // Speicher freigeben
    return 0;
}
```

## Erklärung
Beim Arbeiten mit `realloc` gibt es einige häufige Fallstricke:

- **NULL-Zeiger**: Wenn `ptr` zu `NULL` ist, wird `realloc` wie `malloc` behandelt, was zu unerwartetem Verhalten führen kann, wenn der Benutzer nicht darauf vorbereitet ist.
- **Speicherlecks**: Wenn die Rückgabe von `realloc` nicht gespeichert wird und ein Fehler auftritt (d.h. `NULL` zurückgegeben wird), könnte der ursprüngliche Speicherblock verloren gehen und nicht freigegeben werden.
- **Datenverlust**: Bei einer Verkleinerung könnte der Inhalt der nicht mehr benötigten Bytes verloren gehen. Es ist ratsam, die neuen Werte sofort nach der Anpassung zu überprüfen.

## Ein-Satz-Zusammenfassung
Die `realloc`-Funktion in C ermöglicht die dynamische Anpassung der Größe eines zuvor allokierten Speicherblocks, wodurch die effiziente Verwaltung von Speicherressourcen erleichtert wird.