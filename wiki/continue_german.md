<!--
Meta Description: # Das Schlüsselwort "continue" in C: Verwendung und Beispiele ## Zusammenfassung Das Schlüsselwort "continue" in der Programmiersprache C wird verwend...
Meta Keywords: continue, schleife, der, das, die
-->

# Das Schlüsselwort "continue" in C: Verwendung und Beispiele

## Zusammenfassung
Das Schlüsselwort "continue" in der Programmiersprache C wird verwendet, um die aktuelle Iteration einer Schleife zu überspringen und direkt zur nächsten Iteration überzugehen.

## Dokumentation
Das "continue"-Statement ist ein Steuerfluss-Statement in C, das in Schleifen (for, while, do-while) eingesetzt wird. Es ermöglicht es einem Programmierer, bestimmte Bedingungen zu prüfen und, falls diese erfüllt sind, die restlichen Anweisungen der aktuellen Schleifeniteration zu überspringen. Stattdessen wird der Kontrollfluss zum Beginn der nächsten Iteration der Schleife weitergeleitet.

### Verwendung
Das "continue"-Statement kann in verschiedenen Schleifen verwendet werden:
- In einer `for`-Schleife: überspringt die restlichen Anweisungen in der aktuellen Iteration und springt zur nächsten Iteration.
- In einer `while`- oder `do-while`-Schleife: überspringt ebenfalls die aktuelle Iteration, wenn es aufgerufen wird.

### Syntax
```c
continue; // in der Schleife
```

## Beispiele

### Beispiel 1: Verwendung in einer for-Schleife
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        if (i % 2 == 0) {
            continue; // überspringt die Ausgabe für gerade Zahlen
        }
        printf("%d ", i); // gibt nur ungerade Zahlen aus
    }
    return 0;
}
```
**Ausgabe:** `1 3 5 7 9`

### Beispiel 2: Verwendung in einer while-Schleife
```c
#include <stdio.h>

int main() {
    int i = 0;
    while (i < 10) {
        i++;
        if (i % 3 == 0) {
            continue; // überspringt die Ausgabe für Vielfache von 3
        }
        printf("%d ", i);
    }
    return 0;
}
```
**Ausgabe:** `1 2 4 5 7 8 10`

## Erklärung
Das "continue"-Statement kann manchmal zu Verwirrung führen, insbesondere wenn es in verschachtelten Schleifen oder in Kombination mit anderen Kontrollflussanweisungen verwendet wird. Ein häufiger Fehler besteht darin, das "continue"-Statement in der falschen Schleife zu platzieren, was zu unerwartetem Verhalten führen kann. Hier sind einige wichtige Punkte zu beachten:

- **Verschachtelte Schleifen:** Wenn "continue" in einer inneren Schleife verwendet wird, hat es nur Auswirkungen auf die innere Schleife und nicht auf die äußere.
- **Lesbarkeit:** Übermäßiger Gebrauch von "continue" kann den Code schwerer lesbar machen. Es ist oft besser, die Logik so zu strukturieren, dass der Code klarer und einfacher zu verstehen ist.

## Ein-Satz-Zusammenfassung
Das "continue"-Statement in C ermöglicht das Überspringen der aktuellen Iteration einer Schleife und den sofortigen Übergang zur nächsten Iteration.