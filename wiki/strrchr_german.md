<!--
Meta Description: # strrchr in C: Die Funktion zum Suchen des letzten Vorkommens eines Zeichens in einer Zeichenkette ## Synopsis Die Funktion `strrchr` in C wird verwe...
Meta Keywords: die, strrchr, das, zeichenkette, ist
-->

# strrchr in C: Die Funktion zum Suchen des letzten Vorkommens eines Zeichens in einer Zeichenkette

## Synopsis
Die Funktion `strrchr` in C wird verwendet, um das letzte Vorkommen eines bestimmten Zeichens in einer Zeichenkette zu finden. Sie ist ein nützliches Werkzeug in der Zeichenverarbeitung und spielt eine wichtige Rolle in der Manipulation von Strings.

## Dokumentation
### Zweck
`strrchr` ist eine Standardbibliotheksfunktion, die in der Header-Datei `<string.h>` definiert ist. Sie sucht von hinten nach vorne in einer Zeichenkette nach dem angegebenen Zeichen und gibt einen Zeiger auf die letzte Stelle zurück, an der dieses Zeichen gefunden wurde.

### Verwendung
Die Funktion hat die folgende Signatur:

```c
char *strrchr(const char *str, int c);
```

- **Parameter**:
  - `str`: Ein Zeiger auf die Zeichenkette, in der gesucht werden soll.
  - `c`: Das Zeichen, nach dem gesucht werden soll. Es wird als `int` übergeben, entspricht aber einem `char`.

- **Rückgabewert**:
  - Ein Zeiger auf das letzte Vorkommen des Zeichens in der Zeichenkette. Wenn das Zeichen nicht gefunden wird, gibt die Funktion `NULL` zurück.

### Details
`strrchr` durchläuft die Zeichenkette von hinten nach vorne. Diese Funktion ist besonders hilfreich, wenn man das letzte Vorkommen eines Zeichens benötigt, zum Beispiel, um den letzten Punkt in einem Dateinamen zu finden. Beachte, dass der gesuchte Charakter als `int` übergeben werden kann, um eine mögliche Umwandlung von `char` zu `int` zu unterstützen.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung von `strrchr`:

### Beispiel 1: Einfaches Finden eines Zeichens
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hallo, Welt!";
    char *result = strrchr(str, 'l');
    if (result != NULL) {
        printf("Das letzte Vorkommen von 'l' ist an Position: %ld\n", result - str);
    } else {
        printf("'l' nicht gefunden.\n");
    }
    return 0;
}
```
**Ausgabe**: Das letzte Vorkommen von 'l' ist an Position: 9

### Beispiel 2: Zeichen nicht gefunden
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hallo, Welt!";
    char *result = strrchr(str, 'x');
    if (result == NULL) {
        printf("'x' nicht gefunden.\n");
    }
    return 0;
}
```
**Ausgabe**: 'x' nicht gefunden.

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von `strrchr` ist, dass der Rückgabewert ein Zeiger auf das gefundene Zeichen oder `NULL` sein kann. Programmierer sollten sicherstellen, dass sie den Rückgabewert auf `NULL` überprüfen, um Fehler zu vermeiden. Achte darauf, dass das gesuchte Zeichen ein `char` und kein String ist – `strrchr` akzeptiert nur ein einzelnes Zeichen.

Ein weiterer Punkt ist, dass die Funktion nur mit nullterminierten Zeichenketten funktioniert und die Zeichenkette nicht modifiziert. Wenn du die Zeichenkette änderst, während du `strrchr` verwendest, kann dies zu undefiniertem Verhalten führen.

## Ein-Satz-Zusammenfassung
Die Funktion `strrchr` in C ermöglicht es, das letzte Vorkommen eines Zeichens in einer Zeichenkette zu finden und gibt einen Zeiger auf diese Position zurück.