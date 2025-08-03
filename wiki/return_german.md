<!--
Meta Description: # Rückgabewert in C: Die "return"-Anweisung verstehen ## Synopsis Die `return`-Anweisung in C ist ein grundlegendes Sprachkonstrukt, das dazu verwende...
Meta Keywords: return, die, funktion, rückgabewert, der
-->

# Rückgabewert in C: Die "return"-Anweisung verstehen

## Synopsis
Die `return`-Anweisung in C ist ein grundlegendes Sprachkonstrukt, das dazu verwendet wird, den Rückgabewert einer Funktion zu definieren und die Kontrolle an den Aufrufer zurückzugeben. Diese Anweisung spielt eine entscheidende Rolle in der Struktur von C-Programmen.

## Dokumentation
Die `return`-Anweisung wird in C verwendet, um:
- Den Wert zurückzugeben, den eine Funktion erzeugt.
- Die Ausführung einer Funktion vorzeitig zu beenden.

### Zweck
Der Hauptzweck von `return` besteht darin, einen Wert an den Aufrufer der Funktion zurückzugeben, was besonders wichtig ist, wenn die Funktion Berechnungen oder Datenverarbeitungen durchführt, die für den weiteren Verlauf des Programms benötigt werden.

### Verwendung
Die allgemeine Syntax der `return`-Anweisung ist wie folgt:
```c
return Ausdruck;
```
Hierbei ist `Ausdruck` optional. Wenn kein Ausdruck angegeben wird, wird `return;` verwendet, um die Kontrolle ohne Rückgabewert an die aufrufende Funktion zurückzugeben.

### Details
- Der Rückgabewert muss mit dem Rückgabetyp der Funktion übereinstimmen. Ein `int`-Rückgabewert kann beispielsweise nur einen `int`-Wert zurückgeben.
- Bei Funktionen ohne Rückgabewert (void-Funktionen) kann `return;` verwendet werden, um die Funktion vorzeitig zu beenden.

## Beispiele
### Beispiel 1: Einfache Rückgabe eines Wertes
```c
#include <stdio.h>

int addiere(int a, int b) {
    return a + b;
}

int main() {
    int summe = addiere(5, 7);
    printf("Die Summe ist: %d\n", summe);
    return 0;
}
```

### Beispiel 2: Vorzeitige Beendigung einer Funktion
```c
#include <stdio.h>

void checkZahl(int zahl) {
    if (zahl < 0) {
        printf("Zahl ist negativ.\n");
        return; // Vorzeitige Beendigung
    }
    printf("Zahl ist positiv: %d\n", zahl);
}

int main() {
    checkZahl(-5);
    checkZahl(10);
    return 0;
}
```

## Erklärung
Einige häufige Fallstricke bei der Verwendung von `return` in C sind:
- **Typenkonflikte**: Stellen Sie sicher, dass der Rückgabewert den richtigen Datentyp hat. Andernfalls kann dies zu unerwartetem Verhalten oder Compilerfehlern führen.
- **Vergessen von `return` in nicht-void-Funktionen**: Wenn eine Funktion einen Wert zurückgeben soll, aber kein `return` verwendet wird, kann es zu undefiniertem Verhalten kommen.
- **Rückgabewert nicht verwendet**: Wenn der Rückgabewert einer Funktion nicht gespeichert oder weiterverarbeitet wird, kann dies die Funktionalität des Programms beeinträchtigen.

## Einzeilensummary
Die `return`-Anweisung in C ermöglicht es, einen Wert aus einer Funktion zurückzugeben und die Kontrolle an den Aufrufer zurückzugeben.