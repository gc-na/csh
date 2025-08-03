<!--
Meta Description: # abs() Funktion in C: Absolute Werte berechnen ## Synopsis Die `abs()` Funktion in C wird verwendet, um den absoluten Wert einer Ganzzahl zu berechne...
Meta Keywords: abs, wert, ist, der, int
-->

# abs() Funktion in C: Absolute Werte berechnen

## Synopsis
Die `abs()` Funktion in C wird verwendet, um den absoluten Wert einer Ganzzahl zu berechnen. Sie ist besonders nützlich, wenn Sie sicherstellen möchten, dass der Wert immer positiv ist, unabhängig von seinem ursprünglichen Vorzeichen.

## Dokumentation
Die `abs()` Funktion gehört zur Standardbibliothek von C und ist in der Header-Datei `<stdlib.h>` definiert. Die Funktion nimmt eine Ganzzahl (int) als Eingabeparameter und gibt den absoluten Wert dieser Zahl zurück. Wenn der übergebene Wert negativ ist, wird der negative Vorzeichen entfernt; wenn er positiv ist, bleibt er unverändert.

### Syntax
```c
#include <stdlib.h>

int abs(int x);
```

### Parameter
- `x`: Eine Ganzzahl, deren absoluter Wert berechnet werden soll.

### Rückgabewert
Die `abs()` Funktion gibt den absoluten Wert von `x` zurück. Bei `x = 0` ergibt sie `0`, bei positiven Werten gibt sie den Wert selbst zurück, und bei negativen Werten wird der Wert ohne Vorzeichen zurückgegeben.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung der `abs()` Funktion:

### Beispiel 1: Grundlegende Verwendung
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int zahl1 = -10;
    int zahl2 = 5;

    printf("Der absolute Wert von %d ist %d\n", zahl1, abs(zahl1));
    printf("Der absolute Wert von %d ist %d\n", zahl2, abs(zahl2));

    return 0;
}
```

### Beispiel 2: Nutzung in einer Berechnung
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int a = -20;
    int b = 15;

    int differenz = abs(a - b);
    printf("Der absolute Unterschied zwischen %d und %d ist %d\n", a, b, differenz);

    return 0;
}
```

## Erklärung
Ein häufiger Fehler beim Einsatz von `abs()` ist die Annahme, dass sie auch für Gleitkommazahlen funktioniert. Dies ist nicht der Fall; um den absoluten Wert einer Fließkommazahl zu berechnen, sollten Sie die Funktion `fabs()` aus der `<math.h>` Header-Datei verwenden. 

Ein weiterer Punkt ist, dass `abs()` nur für `int`-Werte definiert ist. Für `long`-Werte können Sie `labs()` und für `long long`-Werte `llabs()` verwenden, die ähnliche Funktionalitäten bieten, jedoch für größere Werte geeignet sind.

Darüber hinaus kann die Verwendung von `abs()` in einer Schleife oder rekursiven Funktion unerwartete Ergebnisse liefern, wenn die Eingabewerte nicht korrekt behandelt werden.

## Einzeilige Zusammenfassung
Die `abs()` Funktion in C berechnet den absoluten Wert einer Ganzzahl und gibt ihn als positive Zahl zurück.