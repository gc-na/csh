<!--
Meta Description: # Die Funktion exp in C: Exponentialfunktion leicht gemacht ## Synopsis Die Funktion `exp` in C berechnet die Exponentialfunktion einer gegebenen Zahl...
Meta Keywords: die, exp, funktion, der, ist
-->

# Die Funktion exp in C: Exponentialfunktion leicht gemacht

## Synopsis
Die Funktion `exp` in C berechnet die Exponentialfunktion einer gegebenen Zahl und ist Teil der mathematischen Bibliothek. Sie gibt den Wert von e (der Basis des natürlichen Logarithmus) erhöht zur Potenz der übergebenen Zahl zurück.

## Dokumentation
Die `exp`-Funktion ist in der Header-Datei `<math.h>` deklariert und hat das folgende Prototyp:

```c
double exp(double x);
```

### Zweck
Die Funktion `exp` wird verwendet, um die Exponentialfunktion \( e^x \) zu berechnen, wobei \( e \) ungefähr 2.71828 ist. Diese Funktion ist besonders nützlich in mathematischen und wissenschaftlichen Berechnungen, insbesondere in der Statistik und der Finanzmathematik.

### Verwendung
Um die `exp`-Funktion zu verwenden, müssen Sie sicherstellen, dass die mathematische Bibliothek in Ihrem Projekt eingebunden ist. Dies geschieht durch das Hinzufügen der Zeile:

```c
#include <math.h>
```

Danach können Sie `exp` in Ihrem Code verwenden, um die Exponentialfunktion zu berechnen.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung der `exp`-Funktion:

### Beispiel 1: Einfache Exponentialberechnung
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 2.0;
    double result = exp(x);
    printf("e^%.2f = %.2f\n", x, result);
    return 0;
}
```
**Ausgabe:**
```
e^2.00 = 7.39
```

### Beispiel 2: Exponentialfunktion mit negativen Werten
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = -1.0;
    double result = exp(x);
    printf("e^%.2f = %.2f\n", x, result);
    return 0;
}
```
**Ausgabe:**
```
e^-1.00 = 0.37
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung der `exp`-Funktion ist das Verständnis ihrer Rückgabewerte für große oder sehr kleine Eingabewerte. Bei sehr großen positiven Werten kann `exp` zu einem Überlauf führen und `inf` zurückgeben. Umgekehrt kann die Eingabe sehr kleiner negativer Werte zu einem Unterlauf führen, was möglicherweise 0 zurückgibt. 

Zusätzlich ist zu beachten, dass die `exp`-Funktion einen `double`-Wert zurückgibt. Daher sollten Sie sicherstellen, dass die Variablen, die den Rückgabewert speichern, ebenfalls vom Typ `double` sind, um Präzisionsverlust zu vermeiden.

## Zusammenfassung in einem Satz
Die `exp`-Funktion in C berechnet die Exponentialfunktion \( e^x \) für einen gegebenen Wert \( x \) und ist unerlässlich für mathematische und wissenschaftliche Berechnungen.