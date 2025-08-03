<!--
Meta Description: # Logarithmusfunktion in C: Verwendung der log-Funktion ## Synopsis Die `log`-Funktion in C ist eine mathematische Funktion, die den natürlichen Logar...
Meta Keywords: der, log, die, funktion, logarithmus
-->

# Logarithmusfunktion in C: Verwendung der log-Funktion

## Synopsis
Die `log`-Funktion in C ist eine mathematische Funktion, die den natürlichen Logarithmus (Basis e) einer gegebenen Zahl berechnet. Diese Funktion ist Teil der Standard-C-Bibliothek und wird häufig in wissenschaftlichen und ingenieurtechnischen Anwendungen verwendet.

## Dokumentation
Die `log`-Funktion gehört zur `<math.h>`-Headerdatei und hat die folgende Syntax:

```c
#include <math.h>
double log(double x);
```

### Zweck
Die `log`-Funktion wird verwendet, um den natürlichen Logarithmus einer Zahl zu berechnen. Der natürliche Logarithmus ist der Logarithmus zur Basis e (ungefähr 2,71828).

### Verwendung
- **Parameter**: Der Parameter `x` muss eine positive Gleitkommazahl sein. Der Aufruf von `log` mit einem negativen Wert oder Null führt zu undefiniertem Verhalten.
- **Rückgabewert**: Die Funktion gibt den natürlichen Logarithmus von `x` zurück. Im Falle eines Fehlers (z.B. Eingabe von 0 oder einer negativen Zahl) wird der Wert `NaN` (not a number) zurückgegeben.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung der `log`-Funktion in C:

### Beispiel 1: Berechnung des natürlichen Logarithmus
```c
#include <stdio.h>
#include <math.h>

int main() {
    double wert = 10.0;
    double logWert = log(wert);
    printf("Der natürliche Logarithmus von %.2f ist %.2f\n", wert, logWert);
    return 0;
}
```

### Beispiel 2: Umgang mit ungültigen Eingaben
```c
#include <stdio.h>
#include <math.h>

int main() {
    double wert = -5.0;
    double logWert = log(wert);
    if (isnan(logWert)) {
        printf("Der natürliche Logarithmus kann nicht für negative Werte berechnet werden.\n");
    }
    return 0;
}
```

## Erklärung
Bei der Verwendung der `log`-Funktion können einige häufige Probleme auftreten:
- **Negative Werte**: Die Eingabe eines negativen Wertes führt zu einem `NaN`-Wert. Es ist wichtig, dies zu überprüfen, um Laufzeitfehler zu vermeiden.
- **Zero-Wert**: Ähnlich wie bei negativen Werten führt die Eingabe von 0 ebenfalls zu einem `NaN`. Nutzen Sie daher immer eine Validierung der Eingabewerte.
- **Falsche Header**: Stellen Sie sicher, dass der Header `<math.h>` in Ihrem Code inkludiert ist, da die `log`-Funktion sonst nicht erkannt wird.

## Einzeiliger Zusammenfassung
Die `log`-Funktion in C berechnet den natürlichen Logarithmus einer positiven Zahl und gibt `NaN` zurück, wenn die Eingabe negativ oder null ist.