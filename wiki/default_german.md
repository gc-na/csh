<!--
Meta Description: # Standardwert in C: Was bedeutet "default"? ## Synopsis In der Programmiersprache C bezieht sich der Begriff "default" häufig auf Standardwerte, insb...
Meta Keywords: der, default, ist, switch, wird
-->

# Standardwert in C: Was bedeutet "default"?

## Synopsis
In der Programmiersprache C bezieht sich der Begriff "default" häufig auf Standardwerte, insbesondere in der Verwendung von switch-Anweisungen, um bestimmte Aktionen zu definieren, wenn kein anderer Fall erfüllt ist.

## Dokumentation
In C wird das Schlüsselwort `default` innerhalb einer `switch`-Anweisung verwendet. Es dient dazu, einen Standardfall zu definieren, der ausgeführt wird, wenn keine der angegebenen Fallbedingungen zutrifft. Der `default`-Fall ist optional und kann an beliebiger Stelle innerhalb der switch-Anweisung platziert werden, sollte jedoch in der Regel am Ende stehen, um die Lesbarkeit zu erhöhen.

### Zweck
Der Zweck des `default`-Schlüssels besteht darin, einen definierten Codeblock bereitzustellen, der ausgeführt wird, wenn keine der vorhergehenden `case`-Bedingungen wahr ist. Dies ermöglicht eine flexible Handhabung unerwarteter Werte oder Zustände.

### Verwendung
Die allgemeine Syntax einer `switch`-Anweisung mit `default` sieht wie folgt aus:

```c
switch (ausdruck) {
    case wert1:
        // Code für Wert 1
        break;
    case wert2:
        // Code für Wert 2
        break;
    default:
        // Code für den Standardfall
}
```

## Beispiele
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung von `default`:

### Beispiel 1: Grundlegende Verwendung von `default`
```c
#include <stdio.h>

int main() {
    int zahl = 3;

    switch (zahl) {
        case 1:
            printf("Die Zahl ist 1.\n");
            break;
        case 2:
            printf("Die Zahl ist 2.\n");
            break;
        default:
            printf("Die Zahl ist weder 1 noch 2.\n");
            break;
    }

    return 0;
}
```

In diesem Beispiel gibt das Programm "Die Zahl ist weder 1 noch 2." aus, da `zahl` den Wert 3 hat.

### Beispiel 2: `default` ohne vorhergehende `case`
```c
#include <stdio.h>

int main() {
    char buchstabe = 'x';

    switch (buchstabe) {
        default:
            printf("Das ist ein unbekannter Buchstabe.\n");
            break;
    }

    return 0;
}
```

Hier wird der `default`-Fall ausgeführt, da es keine `case`-Bedingungen gibt.

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `default` in `switch`-Anweisungen ist die Platzierung des `break`-Statements. Wenn `break` weggelassen wird, wird der Code in den nachfolgenden `case`-Bedingungen weiterhin ausgeführt (sog. "fall-through"). Dies kann unbeabsichtigte Ergebnisse zur Folge haben.

Zusätzlich ist zu beachten, dass der `default`-Fall nicht zwingend erforderlich ist. Wenn er weggelassen wird und kein `case` zutrifft, wird die `switch`-Anweisung einfach beendet, ohne dass ein Code ausgeführt wird.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort `default` in C definiert einen Standardfall innerhalb von `switch`-Anweisungen, der ausgeführt wird, wenn keine der spezifizierten `case`-Bedingungen erfüllt ist.