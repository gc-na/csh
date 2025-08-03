<!--
Meta Description: # sqrt - Die Quadratwurzel-Funktion in C ## Synopsis Die `sqrt`-Funktion in C berechnet die Quadratwurzel einer gegebenen Zahl und ist Teil der Mathem...
Meta Keywords: die, ist, sqrt, funktion, quadratwurzel
-->

# sqrt - Die Quadratwurzel-Funktion in C

## Synopsis
Die `sqrt`-Funktion in C berechnet die Quadratwurzel einer gegebenen Zahl und ist Teil der Mathematikbibliothek. Sie wird häufig in mathematischen Berechnungen verwendet.

## Dokumentation
Die `sqrt`-Funktion ist in der Header-Datei `<math.h>` definiert und hat die folgende Syntax:

```c
#include <math.h>

double sqrt(double x);
```

### Zweck
Die Funktion `sqrt` dient dazu, die Quadratwurzel einer nicht-negativen Zahl `x` zu berechnen. Wenn `x` kleiner als 0 ist, wird das Verhalten nicht definiert, und die Funktion kann NaN (Not a Number) zurückgeben.

### Verwendung
Um die `sqrt`-Funktion zu verwenden, müssen Sie sicherstellen, dass Sie die Header-Datei `<math.h>` in Ihrem C-Programm einbinden. Die Rückgabewerte sind vom Typ `double`.

### Rückgabewerte
- Bei Eingabe von `x >= 0` gibt die Funktion die Quadratwurzel von `x` zurück.
- Bei Eingabe von `x < 0` ist das Ergebnis undefiniert.

## Beispiele
### Einfaches Beispiel
Hier ist ein einfaches Beispiel, das die Verwendung der `sqrt`-Funktion zeigt:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double number = 16.0;
    double result = sqrt(number);
    printf("Die Quadratwurzel von %.2f ist %.2f\n", number, result);
    return 0;
}
```

### Beispiel mit negativer Zahl
Ein Beispiel, das das Verhalten bei negativen Zahlen demonstriert:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double number = -4.0;
    double result = sqrt(number);
    printf("Die Quadratwurzel von %.2f ist %.f\n", number, result); // Ausgabe kann NaN sein
    return 0;
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung der `sqrt`-Funktion ist die Eingabe negativer Zahlen. Da die Quadratwurzel einer negativen Zahl im Bereich der reellen Zahlen nicht definiert ist, sollten Sie sicherstellen, dass der Eingabewert immer nicht-negativ ist. 

Zusätzlich ist es wichtig zu beachten, dass die `sqrt`-Funktion eine Gleitpunktberechnung durchführt, was bedeutet, dass die Genauigkeit der Berechnung durch den Wert von `x` beeinflusst werden kann. Bei sehr großen Zahlen ist die Rückgabe möglicherweise nicht exakt.

## Ein Satz Zusammenfassung
Die `sqrt`-Funktion in C berechnet die Quadratwurzel einer nicht-negativen Zahl und ist ein wichtiges Werkzeug für mathematische Berechnungen.