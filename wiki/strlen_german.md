<!--
Meta Description: # strlen in C: Die Funktion zur Bestimmung der Länge von Strings ## Synopsis Die Funktion `strlen` in C wird verwendet, um die Länge eines Strings zu ...
Meta Keywords: die, der, strlen, strings, string
-->

# strlen in C: Die Funktion zur Bestimmung der Länge von Strings

## Synopsis
Die Funktion `strlen` in C wird verwendet, um die Länge eines Strings zu ermitteln, der in einem `char`-Array gespeichert ist. Sie zählt die Anzahl der Zeichen bis zum Nullterminator (`'\0'`), der das Ende des Strings markiert.

## Dokumentation
### Zweck
`strlen` ist Teil der Standardbibliothek `<string.h>` und dient dazu, die Anzahl der Zeichen in einem String zu bestimmen. Sie ist ein nützliches Werkzeug in der String-Manipulation, um sicherzustellen, dass Sie die korrekten Längen bei der Verarbeitung von Strings verwenden.

### Verwendung
Die Funktion wird wie folgt deklariert:

```c
#include <string.h>

size_t strlen(const char *str);
```

#### Parameter
- `str`: Ein Zeiger auf den String, dessen Länge bestimmt werden soll. Der String muss mit einem Nullterminator enden.

#### Rückgabewert
- Die Funktion gibt die Länge des Strings (ohne den Nullterminator) vom Typ `size_t` zurück. Bei einem leeren String gibt `strlen` den Wert `0` zurück.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `strlen`:

### Beispiel 1: Bestimmung der Länge eines einfachen Strings
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *text = "Hallo Welt";
    size_t length = strlen(text);
    printf("Länge des Strings: %zu\n", length); // Ausgabe: Länge des Strings: 10
    return 0;
}
```

### Beispiel 2: Leerer String
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *text = "";
    size_t length = strlen(text);
    printf("Länge des leeren Strings: %zu\n", length); // Ausgabe: Länge des leeren Strings: 0
    return 0;
}
```

## Erklärung
### Häufige Fallstricke
- **Nullzeiger**: Die Funktion `strlen` erwartet einen gültigen Zeiger auf einen String. Wenn ein Nullzeiger (`NULL`) übergeben wird, führt dies zu undefiniertem Verhalten.
- **Nicht terminierte Strings**: Wenn der String nicht korrekt mit einem Nullterminator endet, kann `strlen` über das Ende des Strings hinaus lesen, was ebenfalls zu undefiniertem Verhalten führt.
- **Speicherüberlauf**: Bei der Verwendung von `strlen` in Kombination mit dynamisch allozierten Strings müssen Sie sicherstellen, dass genügend Speicher vorhanden ist und der String korrekt terminiert ist.

### Zusätzliche Hinweise
- `strlen` zählt nur die sichtbaren Zeichen und ignoriert den Nullterminator. Dies bedeutet, dass es nützlich ist, die tatsächliche Anzahl der verwendeten Zeichen in Textoperationen zu kennen.
- Die Rückgabewerte von `strlen` sind vom Typ `size_t`, was bedeutet, dass sie die Größe in Bytes darstellen und für die Verwendung in Indizes und Schleifen geeignet sind.

## Ein-Satz-Zusammenfassung
Die `strlen`-Funktion in C bestimmt die Länge eines Strings, indem sie die Anzahl der Zeichen bis zum Nullterminator zählt.