<!--
Meta Description: # strcmp – Der Vergleich von C-Strings in C ## Synopsis Die Funktion `strcmp` in C wird verwendet, um zwei C-Strings (nullterminierte Zeichenfolgen) l...
Meta Keywords: die, ist, strcmp, strings, der
-->

# strcmp – Der Vergleich von C-Strings in C

## Synopsis
Die Funktion `strcmp` in C wird verwendet, um zwei C-Strings (nullterminierte Zeichenfolgen) lexikographisch zu vergleichen. Sie ist ein essentielles Werkzeug für die String-Manipulation in der Programmiersprache C.

## Dokumentation
Die Funktion `strcmp` gehört zur Standardbibliothek von C und ist in der Header-Datei `<string.h>` definiert. Ihr Hauptzweck besteht darin, zwei Strings zu vergleichen und eine Ganzzahl zurückzugeben, die das Ergebnis des Vergleichs angibt.

### Syntax
```c
int strcmp(const char *str1, const char *str2);
```

### Parameter
- `str1`: Ein Zeiger auf den ersten C-String, der verglichen werden soll.
- `str2`: Ein Zeiger auf den zweiten C-String, der verglichen werden soll.

### Rückgabewert
- Ein negativer Wert, wenn `str1` kleiner als `str2` ist.
- Null (0), wenn `str1` gleich `str2` ist.
- Ein positiver Wert, wenn `str1` größer als `str2` ist.

### Zweck
`strcmp` wird häufig verwendet, um die Gleichheit von Strings zu überprüfen oder um Strings in sortierten Datenstrukturen zu ordnen.

## Beispiele
### Beispiel 1: Einfache Verwendung
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *string1 = "Hallo";
    const char *string2 = "Welt";
    
    int result = strcmp(string1, string2);
    
    if (result < 0) {
        printf("\"%s\" ist kleiner als \"%s\"\n", string1, string2);
    } else if (result > 0) {
        printf("\"%s\" ist größer als \"%s\"\n", string1, string2);
    } else {
        printf("\"%s\" ist gleich \"%s\"\n", string1, string2);
    }
    
    return 0;
}
```

### Beispiel 2: Vergleich von identischen Strings
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *string1 = "Test";
    const char *string2 = "Test";
    
    if (strcmp(string1, string2) == 0) {
        printf("Die Strings sind identisch.\n");
    } else {
        printf("Die Strings sind unterschiedlich.\n");
    }
    
    return 0;
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `strcmp` ist, dass die Funktion die Groß- und Kleinschreibung berücksichtigt. Das bedeutet, dass "Hallo" und "hallo" als unterschiedlich angesehen werden. Um eine fallunabhängige Vergleichsfunktion zu verwenden, sollte `strcasecmp` (oder `stricmp` in einigen Implementierungen) verwendet werden.

Ein weiterer Punkt zu beachten ist, dass die Funktion `strcmp` davon ausgeht, dass die übergebenen Strings korrekt nullterminiert sind. Ein fehlender Nullterminator kann zu undefiniertem Verhalten führen.

## Ein-Satz-Zusammenfassung
Die Funktion `strcmp` in C vergleicht zwei C-Strings lexikographisch und gibt einen Wert zurück, der angibt, ob der erste String kleiner, gleich oder größer als der zweite String ist.