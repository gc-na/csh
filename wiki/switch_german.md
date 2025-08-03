<!--
Meta Description: # switch-Anweisung in C: Eine umfassende Anleitung ## Synopsis Die `switch`-Anweisung in C ermöglicht eine effiziente Mehrfachverzweigung, indem sie e...
Meta Keywords: case, switch, break, der, eine
-->

# switch-Anweisung in C: Eine umfassende Anleitung

## Synopsis
Die `switch`-Anweisung in C ermöglicht eine effiziente Mehrfachverzweigung, indem sie eine Variable mit mehreren möglichen Werten vergleicht und entsprechend einem der definierten Fälle eine Aktion ausführt.

## Dokumentation
Die `switch`-Anweisung ist eine Kontrollstruktur, die es ermöglicht, basierend auf dem Wert einer Variablen unterschiedliche Codeabschnitte auszuführen. Sie ist besonders nützlich, wenn eine Variable mehrere mögliche Werte annehmen kann und für jeden Wert eine spezifische Aktion erforderlich ist.

### Syntax
```c
switch (ausdruck) {
    case wert1:
        // Codeblock für wert1
        break;
    case wert2:
        // Codeblock für wert2
        break;
    ...
    default:
        // Codeblock für alle anderen Werte
}
```

### Zweck
Der Hauptzweck der `switch`-Anweisung besteht darin, die Lesbarkeit und Wartbarkeit des Codes zu verbessern, insbesondere wenn viele `if-else`-Anweisungen erforderlich wären.

### Verwendung
- Der `switch`-Ausdruck kann einen `int`, `char` oder einen `enum`-Wert annehmen.
- Jeder `case`-Block beendet sich idealerweise mit einem `break`, um ein „Durchfallen“ in die nächsten Fälle zu vermeiden.
- Der `default`-Block wird ausgeführt, wenn keiner der `case`-Werte übereinstimmt.

## Beispiele

### Einfaches Beispiel
```c
#include <stdio.h>

int main() {
    int tag = 3;

    switch (tag) {
        case 1:
            printf("Montag\n");
            break;
        case 2:
            printf("Dienstag\n");
            break;
        case 3:
            printf("Mittwoch\n");
            break;
        default:
            printf("Ungültiger Tag\n");
    }

    return 0;
}
```

### Beispiel ohne `break`
```c
#include <stdio.h>

int main() {
    int zahl = 2;

    switch (zahl) {
        case 1:
            printf("Eins\n");
        case 2:
            printf("Zwei\n");
        case 3:
            printf("Drei\n");
            break;
        default:
            printf("Ungültige Zahl\n");
    }

    return 0;
}
```
*Ausgabe:*
```
Zwei
Drei
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von `switch` ist, dass das Fehlen eines `break`-Befehls dazu führt, dass der Code in die folgenden `case`-Blöcke „durchfällt“. Dies kann erwünscht sein, sollte jedoch bewusst eingesetzt werden, um unerwartete Ergebnisse zu vermeiden.

### Gemeinsame Fehler
- **Vergessen des `break`:** Wenn `break` weggelassen wird, wird der Code des nächsten `case` weiter ausgeführt.
- **Falsche Datentypen:** `switch` kann nur mit ganzzahligen Typen oder `char`-Typen verwendet werden. Verwenden Sie keine Gleitkommazahlen oder Strings.

## Einzeilige Zusammenfassung
Die `switch`-Anweisung in C ermöglicht eine einfache und klare Mehrfachverzweigung basierend auf dem Wert einer Variablen.