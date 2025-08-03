<!--
Meta Description: # Die Funktion "floor" in C: Abrunden von Fließkommazahlen ## Synopsis Die `floor`-Funktion in C rundet eine Fließkommazahl auf die größte ganze Zahl ...
Meta Keywords: floor, die, funktion, der, zahl
-->

# Die Funktion "floor" in C: Abrunden von Fließkommazahlen

## Synopsis
Die `floor`-Funktion in C rundet eine Fließkommazahl auf die größte ganze Zahl ab, die kleiner oder gleich der gegebenen Zahl ist.

## Dokumentation
Die `floor`-Funktion gehört zur mathematischen Bibliothek von C und ist in der Header-Datei `<math.h>` deklariert. Sie wird häufig verwendet, um Fließkommazahlen in Ganzzahlen zu konvertieren, indem sie auf die nächstliegende kleinere ganze Zahl abgerundet wird.

### Zweck
Die Funktion dient dazu, Fließkommazahlen zu verarbeiten, indem sie sicherstellt, dass das Ergebnis immer eine ganze Zahl ist, die nicht größer als der ursprüngliche Wert ist.

### Verwendung
Die Syntax der `floor`-Funktion lautet:

```c
double floor(double x);
```

**Parameter:**
- `x`: Die Fließkommazahl, die abgerundet werden soll.

**Rückgabewert:**
- Die `floor`-Funktion gibt den abgerundeten Wert von `x` zurück. Der Rückgabewert hat den Datentyp `double`.

### Beispiel
Hier sind einige grundlegende Beispiele für die Verwendung der `floor`-Funktion:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double zahl1 = 3.7;
    double zahl2 = -3.7;
    double zahl3 = 2.0;

    printf("floor(%.1f) = %.1f\n", zahl1, floor(zahl1)); // Ausgabe: floor(3.7) = 3.0
    printf("floor(%.1f) = %.1f\n", zahl2, floor(zahl2)); // Ausgabe: floor(-3.7) = -4.0
    printf("floor(%.1f) = %.1f\n", zahl3, floor(zahl3)); // Ausgabe: floor(2.0) = 2.0

    return 0;
}
```

### Erklärung
Einige häufige Fallstricke und wichtige Hinweise zur Verwendung der `floor`-Funktion:

- **Negative Zahlen:** Die `floor`-Funktion rundet negative Fließkommazahlen auf die nächstliegende kleinere ganze Zahl ab. Zum Beispiel wird `floor(-3.7` zu `-4.0` und nicht zu `-3.0`.
- **Ganzzahlige Werte:** Wenn der Wert bereits eine ganze Zahl ist, bleibt das Ergebnis unverändert. `floor(2.0)` ergibt `2.0`.
- **Datentyp:** Achten Sie darauf, dass der Rückgabewert der `floor`-Funktion vom Typ `double` ist, auch wenn das Ergebnis eine ganze Zahl ist. Möglicherweise müssen Sie das Ergebnis in einen anderen Datentyp umwandeln, wenn Sie damit weiterarbeiten möchten.

## Ein Satz Zusammenfassung
Die `floor`-Funktion in C rundet Fließkommazahlen auf die nächstliegende kleinere ganze Zahl ab und ist eine nützliche Funktion in der mathematischen Verarbeitung.