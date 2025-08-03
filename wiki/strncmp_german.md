<!--
Meta Description: # strncmp in C: Die Funktion zum Vergleichen von Zeichenfolgen ## Synopsis Die Funktion `strncmp` in C wird verwendet, um zwei Zeichenfolgen lexikogra...
Meta Keywords: die, zeichenfolgen, der, strncmp, ist
-->

# strncmp in C: Die Funktion zum Vergleichen von Zeichenfolgen

## Synopsis
Die Funktion `strncmp` in C wird verwendet, um zwei Zeichenfolgen lexikografisch zu vergleichen, und zwar bis zu einer bestimmten Anzahl von Zeichen. Diese Funktion ist besonders nützlich, wenn Sie nur einen Teil der Zeichenfolgen vergleichen möchten.

## Dokumentation
### Zweck
Die `strncmp`-Funktion vergleicht die ersten n Zeichen zweier C-Zeichenfolgen und gibt zurück, ob sie gleich sind, oder ob eine der Zeichenfolgen lexikografisch kleiner oder größer ist.

### Verwendung
Die Funktion ist in der Header-Datei `<string.h>` definiert und hat die folgende Syntax:

```c
int strncmp(const char *str1, const char *str2, size_t n);
```

#### Parameter
- `str1`: Ein Zeiger auf die erste Zeichenfolge.
- `str2`: Ein Zeiger auf die zweite Zeichenfolge.
- `n`: Die maximale Anzahl der Zeichen, die verglichen werden sollen.

#### Rückgabewert
Die Funktion gibt einen ganzzahligen Wert zurück:
- Ein Wert kleiner als 0, wenn `str1` kleiner als `str2` ist.
- 0, wenn beide Zeichenfolgen gleich sind.
- Ein Wert größer als 0, wenn `str1` größer als `str2` ist.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `strncmp`:

### Beispiel 1: Einfacher Vergleich
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hallo";
    const char *str2 = "Hallo Welt";
    
    int result = strncmp(str1, str2, 5);
    if (result == 0) {
        printf("Die ersten 5 Zeichen sind gleich.\n");
    } else {
        printf("Die ersten 5 Zeichen sind unterschiedlich.\n");
    }
    return 0;
}
```

### Beispiel 2: Teilvergleich
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Apfel";
    const char *str2 = "Apfelbaum";
    
    if (strncmp(str1, str2, 3) == 0) {
        printf("Die ersten 3 Zeichen sind gleich.\n");
    }
    return 0;
}
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von `strncmp` ist, dass die Funktion nicht die gesamte Länge der Zeichenfolgen berücksichtigt. Wenn `n` kleiner ist als die tatsächliche Länge der Zeichenfolgen, wird nur der angegebene Teil verglichen. Dies kann dazu führen, dass zwei unterschiedliche Zeichenfolgen als gleich angesehen werden, wenn die ersten `n`-Zeichen identisch sind.

Ein weiteres wichtiges Detail ist, dass `strncmp` die Nullterminierung (`'\0'`) der Zeichenfolgen beachtet. Wenn eine der Zeichenfolgen kürzer ist als `n`, wird der Vergleich an dieser Stelle beendet.

## Einzeiliger Überblick
Die Funktion `strncmp` vergleicht die ersten n Zeichen zweier Zeichenfolgen und gibt an, ob sie gleich sind oder nicht.