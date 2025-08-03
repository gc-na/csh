<!--
Meta Description: # strchr – Die C-Funktion zur Zeichenfindung in Strings ## Synopsis Die Funktion `strchr` in C wird verwendet, um das erste Vorkommen eines bestimmten...
Meta Keywords: string, das, die, strchr, zeichen
-->

# strchr – Die C-Funktion zur Zeichenfindung in Strings

## Synopsis
Die Funktion `strchr` in C wird verwendet, um das erste Vorkommen eines bestimmten Zeichens in einem Null-terminierten String zu finden.

## Dokumentation
### Zweck
Die `strchr`-Funktion sucht in einem gegebenen String nach dem ersten Auftreten eines angegebenen Zeichens und gibt einen Zeiger auf die Position des Zeichens im String zurück.

### Verwendung
Die Funktion hat die folgende Signatur:

```c
char *strchr(const char *str, int c);
```

#### Parameter
- `str`: Ein Zeiger auf den Null-terminierten String, in dem gesucht werden soll.
- `c`: Das Zeichen, nach dem gesucht wird, als `int` dargestellt. 

#### Rückgabewert
- Gibt einen Zeiger auf das erste Vorkommen des Zeichens `c` im String `str` zurück.
- Wenn das Zeichen nicht gefunden wird, wird `NULL` zurückgegeben.

### Details
- Die `strchr`-Funktion ist Teil der Standardbibliothek `<string.h>`.
- Das gesuchte Zeichen `c` sollte als `char` interpretiert werden, wird jedoch als `int` übergeben, um die korrekte Handhabung von EOF (End of File) zu ermöglichen.
- Die Suche ist case-sensitive; das bedeutet, dass 'a' und 'A' als unterschiedliche Zeichen behandelt werden.

## Beispiele

### Beispiel 1: Grundlegende Verwendung
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *string = "Hallo Welt";
    char *result = strchr(string, 'W');

    if (result) {
        printf("Das Zeichen 'W' gefunden an Position: %ld\n", result - string);
    } else {
        printf("Das Zeichen 'W' nicht gefunden.\n");
    }

    return 0;
}
```

### Beispiel 2: Zeichen nicht gefunden
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *string = "Hallo Welt";
    char *result = strchr(string, 'x');

    if (result) {
        printf("Das Zeichen 'x' gefunden.\n");
    } else {
        printf("Das Zeichen 'x' nicht gefunden.\n");
    }

    return 0;
}
```

## Erklärung
- Ein häufiger Fehler ist die Annahme, dass `strchr` ein Zeichen zurückgibt, wenn es nicht im String vorhanden ist. Tatsächlich gibt es `NULL` zurück, was in vielen Fällen zu einem Segmentation Fault führen kann, wenn nicht überprüft wird, ob der Rückgabewert `NULL` ist, bevor darauf zugegriffen wird.
- Beachten Sie auch, dass `strchr` auf das erste Vorkommen des Zeichens sucht. Wenn mehrere Vorkommen vorhanden sind, wird nur das erste zurückgegeben.

## Zusammenfassung in einem Satz
Die Funktion `strchr` in C ermöglicht es, das erste Vorkommen eines bestimmten Zeichens in einem String zu finden und gibt einen Zeiger auf dessen Position zurück.