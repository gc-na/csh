<!--
Meta Description: # fabs – Die Funktion zur Berechnung des Absolutwerts in C ## Synopsis Die `fabs`-Funktion in C wird verwendet, um den Absolutwert einer Fließkommazah...
Meta Keywords: fabs, ist, die, von, num
-->

# fabs – Die Funktion zur Berechnung des Absolutwerts in C

## Synopsis
Die `fabs`-Funktion in C wird verwendet, um den Absolutwert einer Fließkommazahl zu berechnen. Sie ist Teil der Mathematikbibliothek und ist insbesondere nützlich in mathematischen Berechnungen, bei denen nur positive Werte relevant sind.

## Dokumentation
Die Funktion `fabs` gehört zur C Standardbibliothek und ist in `<math.h>` definiert. Sie hat folgende Syntax:

```c
double fabs(double x);
```

### Zweck
`fabs` berechnet den Absolutwert einer gegebenen Fließkommazahl `x`. Der Rückgabewert ist der Betrag von `x`, wobei negative Werte in positive umgewandelt werden.

### Verwendung
Um die `fabs`-Funktion zu verwenden, muss die Mathematikbibliothek eingebunden werden. Dazu wird die Header-Datei `<math.h>` benötigt. Die Funktion kann in verschiedenen mathematischen Kontexten eingesetzt werden, z.B. in Algorithmen, die positive Werte erfordern.

### Rückgabewerte
- Wenn `x` positiv oder null ist, gibt `fabs` `x` zurück.
- Wenn `x` negativ ist, gibt `fabs` den positiven Wert von `x` zurück.
- Im Falle von NaN (Not a Number) gibt `fabs` NaN zurück.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung von `fabs`:

### Beispiel 1: Einfacher Absolutwert
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = -5.3;
    printf("Der Absolutwert von %.2f ist %.2f\n", num, fabs(num));
    return 0;
}
```

### Beispiel 2: Absolutwert von Null
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 0.0;
    printf("Der Absolutwert von %.2f ist %.2f\n", num, fabs(num));
    return 0;
}
```

### Beispiel 3: Absolutwert einer positiven Zahl
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 3.14;
    printf("Der Absolutwert von %.2f ist %.2f\n", num, fabs(num));
    return 0;
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `fabs` ist, dass man vergisst, die Header-Datei `<math.h>` einzubinden, was zu einem Kompilierungsfehler führt. Ein weiterer Punkt ist, dass `fabs` nur für den Datentyp `double` geeignet ist. Für andere Datentypen wie `float` oder `long double` stehen die Funktionen `fabsf` und `fabsl` zur Verfügung. Es ist wichtig, darauf zu achten, dass die Rückgabewerte von `fabs` für mathematische Operationen in der richtigen Form verwendet werden.

## Zusammenfassung
Die `fabs`-Funktion in C ist eine praktische Methode zur Berechnung des Absolutwerts einer Fließkommazahl und ist einfach zu verwenden, wenn die Mathematikbibliothek korrekt eingebunden ist.