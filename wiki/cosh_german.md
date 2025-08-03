<!--
Meta Description: # cosh – Die Hyperbolische Kosinusfunktion in C ## Synopsis Die Funktion `cosh` in der Programmiersprache C berechnet den hyperbolischen Kosinus eines...
Meta Keywords: cosh, die, der, funktion, double
-->

# cosh – Die Hyperbolische Kosinusfunktion in C

## Synopsis
Die Funktion `cosh` in der Programmiersprache C berechnet den hyperbolischen Kosinus eines gegebenen Wertes. Sie ist Teil der Mathematikbibliothek `<math.h>` und eignet sich zur Verarbeitung von mathematischen Funktionen in wissenschaftlichen Anwendungen.

## Dokumentation
Die `cosh`-Funktion hat die folgende Signatur:

```c
#include <math.h>
double cosh(double x);
```

### Zweck
Der Zweck der `cosh`-Funktion ist es, den hyperbolischen Kosinus eines Wertes `x` zu berechnen. Der hyperbolische Kosinus wird definiert als:

\[ \cosh(x) = \frac{e^x + e^{-x}}{2} \]

### Verwendung
Um die `cosh`-Funktion zu verwenden, müssen Sie die Header-Datei `<math.h>` inkludieren. Die Funktion erwartet einen `double`-Wert und gibt ebenfalls einen `double`-Wert zurück, der den hyperbolischen Kosinus von `x` darstellt.

### Details
- Rückgabewert: Bei erfolgreicher Berechnung gibt `cosh` den hyperbolischen Kosinus des Eingabewertes zurück.
- Fehlerbehandlung: Die Funktion gibt nicht `NAN` (Not a Number) zurück, es sei denn, der Eingabewert ist ungültig, was in der Regel nicht der Fall ist, da `cosh` für alle reellen Zahlen definiert ist.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung der `cosh`-Funktion:

### Beispiel 1: Grundlegende Verwendung
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 1.0;
    double result = cosh(x);
    printf("cosh(%.1f) = %.2f\n", x, result);
    return 0;
}
```
**Ausgabe:**
```
cosh(1.0) = 1.54
```

### Beispiel 2: Negative Eingabewerte
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = -2.0;
    double result = cosh(x);
    printf("cosh(%.1f) = %.2f\n", x, result);
    return 0;
}
```
**Ausgabe:**
```
cosh(-2.0) = 3.76
```

### Beispiel 3: Große Werte
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 1000.0;
    double result = cosh(x);
    printf("cosh(%.1f) = %.2f\n", x, result);
    return 0;
}
```
**Ausgabe:**
```
cosh(1000.0) = ∞
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von `cosh` ist das Verhalten bei großen oder sehr kleinen Werten. Für sehr große Werte (z. B. über 709) kann die Funktion `cosh` aufgrund der begrenzten Genauigkeit von Gleitkommazahlen im C zu `∞` (Unendlichkeit) führen. Bei sehr kleinen Werten, die gegen Null gehen, wird das Ergebnis jedoch korrekt berechnet und sollte positiv sein.

Ein weiterer Punkt ist, dass `cosh` für negative Werte das gleiche Ergebnis liefert wie für die entsprechenden positiven Werte, da die Funktion eine gerade Funktion ist.

## Ein-Satz-Zusammenfassung
Die `cosh`-Funktion in C berechnet den hyperbolischen Kosinus eines Wertes und ist Teil der Mathematikbibliothek `<math.h>`.