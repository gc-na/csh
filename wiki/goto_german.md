<!--
Meta Description: # Der goto-Befehl in C: Verwendung, Beispiele und häufige Fehler ## Synopsis Der `goto`-Befehl in C ermöglicht es Entwicklern, den Programmfluss durch...
Meta Keywords: goto, der, code, die, sprung
-->

# Der goto-Befehl in C: Verwendung, Beispiele und häufige Fehler

## Synopsis
Der `goto`-Befehl in C ermöglicht es Entwicklern, den Programmfluss durch Sprünge zu bestimmten Markierungen zu steuern. Obwohl er flexibel ist, kann übermäßiger Gebrauch zu unübersichtlichem Code führen.

## Dokumentation
Der `goto`-Befehl wird verwendet, um den Programmfluss an eine angegebene Stelle im Code zu springen. Die Syntax für `goto` besteht aus dem Schlüsselwort `goto` gefolgt von einer Markierung, die im Code definiert ist. Hier ist die grundlegende Syntax:

```c
goto markierung;
...
markierung: 
// Code, der nach dem Sprung ausgeführt wird
```

### Zweck
Der `goto`-Befehl kann nützlich sein, um aus tief verschachtelten Schleifen oder Bedingungen auszubrechen. Er sollte jedoch mit Bedacht verwendet werden, um die Lesbarkeit des Codes nicht zu beeinträchtigen.

### Verwendung
1. **Markierungen definieren**: Eine Markierung wird durch ein Bezeichner gefolgt von einem Doppelpunkt definiert.
2. **Sprünge ausführen**: Der `goto`-Befehl springt zur definierten Markierung im Code.

## Beispiele

### Beispiel 1: Einfacher Sprung
```c
#include <stdio.h>

int main() {
    printf("Vor dem Sprung\n");
    goto hier_springen;
    printf("Dieser Code wird übersprungen\n");
    
hier_springen:
    printf("Nach dem Sprung\n");
    
    return 0;
}
```
**Ausgabe:**
```
Vor dem Sprung
Nach dem Sprung
```

### Beispiel 2: Verwendung in Schleifen
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        if (i == 3) {
            goto ende; // springe zum Ende der Schleife
        }
        printf("%d\n", i);
    }
    
ende:
    printf("Schleife beendet.\n");
    
    return 0;
}
```
**Ausgabe:**
```
0
1
2
Schleife beendet.
```

## Erklärung
Obwohl `goto` eine mächtige Anweisung ist, kann sie den Code unleserlich machen, wenn sie nicht sparsam verwendet wird. Einige häufige Fallstricke sind:

- **Verlust der Kontrolle**: Übermäßige Verwendung kann zu „Spaghetti-Code“ führen, wo der Programmfluss schwer zu verfolgen ist.
- **Unvollständige Sprünge**: Ein Sprung kann unerwartete Nebenwirkungen haben, wenn Variablen nicht in der erwarteten Reihenfolge initialisiert werden.
- **Fehlende Struktur**: Der Einsatz von `goto` kann die Struktur und Logik des Codes untergraben, die durch andere Kontrollstrukturen wie Schleifen und Bedingungen besser ausgedrückt werden können.

## Einzeiler Zusammenfassung
Der `goto`-Befehl in C ermöglicht Springen zu definierten Markierungen, sollte jedoch mit Vorsicht verwendet werden, um die Lesbarkeit des Codes zu bewahren.