<!--
Meta Description: # strstr in C: String-Suchfunktion für Zeichenfolgen ## Synopsis Die Funktion `strstr` in C wird verwendet, um die erste Vorkommen einer Teilzeichenfo...
Meta Keywords: die, strstr, der, needle, char
-->

# strstr in C: String-Suchfunktion für Zeichenfolgen

## Synopsis
Die Funktion `strstr` in C wird verwendet, um die erste Vorkommen einer Teilzeichenfolge innerhalb einer Zeichenkette zu finden. Sie ist Teil der Standardbibliothek `<string.h>` und bietet eine effiziente Möglichkeit, nach Substrings zu suchen.

## Dokumentation
Die Funktion `strstr` hat die folgende Signatur:

```c
char *strstr(const char *haystack, const char *needle);
```

### Zweck
`strstr` durchsucht die Zeichenkette `haystack` nach der ersten Vorkommen der Teilzeichenfolge `needle`. Wenn `needle` gefunden wird, gibt die Funktion einen Zeiger auf den Beginn der gefundenen Teilzeichenfolge zurück. Andernfalls gibt sie `NULL` zurück.

### Verwendung
- **Header-Datei**: Um `strstr` zu verwenden, müssen Sie die Header-Datei `<string.h>` einfügen.
- **Rückgabewert**: Der Rückgabewert ist vom Typ `char*`. Bei Erfolg zeigt er auf die Position der Teilzeichenfolge in der Hauptzeichenkette. Bei Misserfolg (`needle` nicht gefunden) wird `NULL` zurückgegeben.
- **Null-terminated Strings**: Beide Eingabezeichenfolgen müssen nullterminiert sein.

### Beispiel
Hier sind einige grundlegende Beispiele für die Verwendung von `strstr`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *haystack = "Hallo Welt";
    const char *needle = "Welt";
    
    char *result = strstr(haystack, needle);
    if (result != NULL) {
        printf("Gefunden: %s\n", result); // Gibt "Welt" aus
    } else {
        printf("Nicht gefunden.\n");
    }

    return 0;
}
```

## Erklärung
### Häufige Fallstricke
- **NULL-Zeiger**: Wenn einer der beiden Parameter NULL ist, führt dies zu undefiniertem Verhalten. Stellen Sie sicher, dass beide Zeiger gültig sind.
- **Leere `needle`**: Wenn `needle` eine leere Zeichenkette ist, gibt `strstr` immer einen Zeiger auf den Anfang von `haystack` zurück.
- **Groß-/Kleinschreibung**: `strstr` unterscheidet nicht zwischen Groß- und Kleinschreibung. Für eine fallunempfindliche Suche müssen Sie zusätzliche Funktionen verwenden.

### Zusätzliche Hinweise
- `strstr` ist nicht threadsicher, wenn es in multithreaded Anwendungen verwendet wird, sollten Sie sicherstellen, dass die Zeichenfolgen nicht gleichzeitig modifiziert werden.
- Die Leistung von `strstr` kann variieren, abhängig von der Implementierung und der Länge der Zeichenfolgen. Für sehr lange Zeichenfolgen oder häufige Aufrufe kann die Suche ineffizient werden.

## Ein-Satz-Zusammenfassung
Die Funktion `strstr` in C sucht nach einer Teilzeichenfolge in einer Zeichenkette und gibt einen Zeiger auf deren erstes Vorkommen oder NULL zurück, wenn die Teilzeichenfolge nicht gefunden wird.